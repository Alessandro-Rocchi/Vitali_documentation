# 8. Technical Implementation & Software Architecture

## 8.1 Core Technology Stack

* **HTML5:** Semantic landmark tags (`<main>`, `<nav>`, `<section>`, `<article>`, `<aside>`) ensure SEO indexability and screen-reader accessibility.
* **CSS3 & Bootstrap 5:** Mobile-first responsive grid system augmented by custom BEM (Block-Element-Modifier) stylesheets.
* **Vanilla ES6+ JavaScript:** Zero-dependency core logic avoids framework obsolescence, maximizes execution speed, and demonstrates foundational programming competencies.
* **Leaflet.js:** Lightweight (42KB) mapping library ideal for custom tile layers and GeoJSON rendering.

## 8.2 Client-Side JavaScript Lifecycle

```javascript
/**
 * Core Application Controller Flow (index.html)
 */
document.addEventListener('DOMContentLoaded', async () => {
    try {
        // 1. Initialize Leaflet Map Instance
        const map = L.map('map-container').setView([48.8566, 2.3522], 13);
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '© OpenStreetMap contributors'
        }).addTo(map);

        // 2. Asynchronous Spatial Hydration
        const geoResponse = await fetch('data/paris.geojson');
        const geoData = await geoResponse.json();

        // 3. Render Vector Points with Dynamic Bindings
        const geoJsonLayer = L.geoJSON(geoData, {
            onEachFeature: (feature, layer) => {
                layer.bindPopup(`
                    <div class="cinematic-popup">
                        <h6>${feature.properties.name}</h6>
                        <p class="text-muted">${feature.properties.movie} (${feature.properties.year})</p>
                        <button class="btn btn-sm btn-primary" onclick="openDetails('${feature.properties.id}')">
                            Explore
                        </button>
                    </div>
                `);
            }
        }).addTo(map);

        // 4. Initialize PinSearch and Filter Listeners
        initFilters(geoData, geoJsonLayer, map);

    } catch (error) {
        console.error('Critical initialization error:', error);
    }
});

/**
 * Progressive Metadata Loader (On-Demand Fetching)
 */
async function openDetails(locationId) {
    const metaResponse = await fetch('data/paris_metadata.json');
    const metadata = await metaResponse.json();
    const item = metadata[locationId];

    if (!item) return;

    // Populate Level 2 Offcanvas DOM elements dynamically
    document.getElementById('offcanvas-title').innerText = item.title;
    document.getElementById('offcanvas-simple').innerText = item.descriptions.simple;
    document.getElementById('offcanvas-medium').innerText = item.descriptions.medium;
    document.getElementById('img-archival').src = item.imagery.archival_still;
    document.getElementById('img-modern').src = item.imagery.modern_photo;

    // Trigger Bootstrap Offcanvas
    const bsOffcanvas = new bootstrap.Offcanvas(document.getElementById('detailsDrawer'));
    bsOffcanvas.show();
}
```
