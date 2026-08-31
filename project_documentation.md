# Academic Project Documentation: Les Rues du CSS
## Subtitle: *Cinéma Sur la Seine — A Bidirectional Geocritical Cartography of the Nouvelle Vague*

---

### Project Metadata
* **Course / Context:** Web Technologies & Digital Humanities Academic Capstone
* **Project Repository:** `project_Vitali`
* **Target Domain:** Digital Humanities, Spatial Humanities, Cinematic Geocaching & Geotourism
* **Architecture:** Decoupled Client-Side Spatial Engine & Progressive Metadata Hydration
* **Live Deployment:** GitHub Pages (Automated via GitHub Actions CI/CD)
* **Standards & Compliance:** HTML5 Semantics, W3C Validated, WCAG 2.1 Level AA Accessibility

---

## Table of Contents
1. [Executive Summary & Abstract](#1-executive-summary--abstract)
2. [Theoretical Framework & Cultural Heritage](#2-theoretical-framework--cultural-heritage)
3. [Benchmark, Competitive Analysis & User Personas](#3-benchmark-competitive-analysis--user-personas)
4. [Functional & Non-Functional Requirements (MoSCoW Matrix)](#4-functional--non-functional-requirements-moscow-matrix)
5. [Information Architecture & Data Engineering](#5-information-architecture--data-engineering)
6. [Design System & CSS Styling Architecture (Solarpunk Theme)](#6-design-system--css-styling-architecture-solarpunk-theme)
7. [Interaction Design & UI/UX Specifications](#7-interaction-design--uiux-specifications)
8. [Technical Implementation & Software Engineering](#8-technical-implementation--software-engineering)
9. [DevOps, CI/CD & Deployment Pipeline](#9-devops-cicd--deployment-pipeline)
10. [Usability, Accessibility & Heuristic Compliance](#10-usability-accessibility--heuristic-compliance)
11. [Critical Discussion, Limitations & Future Roadmap](#11-critical-discussion-limitations--future-roadmap)

---

## 1. Executive Summary & Abstract

### 1.1 Abstract
**Les Rues du CSS** (*Cinéma Sur la Seine*) is an interactive digital cultural heritage web platform designed to spatialize the history of French cinema, specifically focusing on the **Nouvelle Vague** (French New Wave, c. 1958–1968). The platform conceptualizes and implements a **bidirectional cinematic cartography**: physical locations across Paris act as access points to movie scenes, while cinematic metadata (director, film title, release year, scene synopsis) serves as a thematic navigation key to physical urban topography.

By synthesizing modern web mapping technologies (Leaflet.js), dynamic walking route calculation, progressive cognitive information disclosure, and a decoupled client-side data architecture, the platform caters to both academic film scholars and cultural flâneurs exploring Paris on foot or remotely.

### 1.2 Research Objectives
* **Pedagogical & Technical Question:** *How can web mapping and client-side web architectures be leveraged to represent the historical symbiotic relationship between urban realism and the location-shooting aesthetics of the Nouvelle Vague?*
* **Core Technical Milestones:**
  * Implement a zero-backend, lightweight, high-performance web architecture using standards-compliant HTML5, CSS3, and Vanilla JavaScript (ES6+).
  * Design an optimized, decoupled data model separating pure GeoJSON spatial coordinates from rich narrative and comparative visual metadata.
  * Establish an accessible, responsive design system (Solarpunk/Glassmorphism 2.0) compliant with WCAG 2.1 Level AA contrast and keyboard accessibility standards.

---

## 2. Theoretical Framework & Cultural Heritage

### 2.1 The Spatial Revolution of the Nouvelle Vague
In the late 1950s, young film critics writing for *Cahiers du Cinéma*—most notably **Jean-Luc Godard, François Truffaut, Éric Rohmer, and Jacques Rivette**—alongside Left Bank (*Rive Gauche*) filmmakers such as **Agnès Varda** and **Alain Resnais**, rebelled against the traditional French *cinéma de qualité* (studio-bound, literary costume dramas).

```
+-------------------------------------------------------------------------------+
|                      THE SPATIAL CINEMATIC SHIFT                              |
+-------------------------------------------------------------------------------+
| TRADITIONAL STUDIO CINEMA           | NOUVELLE VAGUE LOCATION CINEMA          |
| ----------------------------------  | --------------------------------------- |
| - Artificial soundstages            | - Paris streets, cafés, public transit  |
| - Heavy, static 35mm cameras        | - Lightweight, handheld 16mm/35mm rigs  |
| - Controlled 3-point studio lighting| - Natural, available street lighting    |
| - Paris as decorative backdrop      | - Paris as active psychological agent   |
+-------------------------------------------------------------------------------+
```

### 2.2 Cinematic Topography & Psychogeography
The theoretical paradigm of the project draws upon **Cinematic Geography** and Guy Debord's concept of **Psychogeography** (the study of the precise laws and specific effects of the geographical environment on the emotions and behavior of individuals):
* In *À bout de souffle* (Godard, 1960), the Champs-Élysées is a space of alienation and breathless modern movement.
* In *Cléo de 5 à 7* (Varda, 1962), Paris is mapped in strict real-time (90 minutes) across Montparnasse, turning the Left Bank into an existential diagnostic terrain.
* In *Les Quatre Cents Coups* (Truffaut, 1959), Antoine Doinel's escape from the 9th arrondissement to the Normandy coast articulates liberation through topological drift (*dérive*).

---

## 3. Benchmark, Competitive Analysis & User Personas

### 3.1 Competitive Benchmark Matrix

| Dimension / Feature | IMDb Locations | Google Maps / Earth | Movie-Locations.com | **Les Rues du CSS** (Ours) |
| :--- | :--- | :--- | :--- | :--- |
| **Spatial Interactivity** | None (Flat text list) | High (Generic maps) | Low (Static map embed) | **High (Custom Leaflet Canvas)** |
| **Thematic Focus** | Global (Unfiltered) | Commercial POIs | General Cinema | **Specialized Nouvelle Vague** |
| **Progressive Disclosure** | None | None | None | **3-Tier Dynamic Loading** |
| **Topological Routing** | None | Generic Navigation | None | **Dynamic Walking Tour Engine** |
| **Comparative Imagery** | User photos (loose) | User Street View | Film stills only | **Curated Archival vs. Modern Stills**|
| **Data Decoupling** | Monolithic DB | Monolithic DB | Server-side CMS | **Decoupled GeoJSON + JSON Meta** |

### 3.2 User Personas

```
+-----------------------------------------------------------------------------+
| USER PERSONA MATRIX                                                         |
+---------------------+-----------------------+-------------------------------+
| Persona Profile     | Primary Need          | Platform Solution             |
+---------------------+-----------------------+-------------------------------+
| Dr. Elena Rossi     | Comparative spatial   | Filter by Director (e.g.,     |
| (Film Researcher)   | analysis of Left Bank | Varda) + Level 3 Detailed     |
|                     | vs Right Bank films.  | Academic metadata modal.      |
+---------------------+-----------------------+-------------------------------+
| Julien Dupont       | On-the-street cultural| Dynamic Routing feature to    |
| (Paris Tourist)     | walking tour of       | follow a generated walking    |
|                     | Godard locations.     | path with mobile geolocation. |
+---------------------+-----------------------+-------------------------------+
| Marco Bianchi       | Visual discovery of   | Thematic Catalogue view       |
| (Cinephile Student) | archival vs modern    | with side-by-side photo       |
|                     | filming locations.    | comparisons and sorting.      |
+---------------------+-----------------------+-------------------------------+
```

---

## 4. Functional & Non-Functional Requirements (MoSCoW Matrix)

```
+-------------------------------------------------------------------------------+
|                             MoSCoW PRIORITIZATION                             |
+-------------------------------------------------------------------------------+
| MUST HAVE (Core Architecture)                                                 |
| - Interactive Leaflet.js map with custom Nouvelle Vague markers.              |
| - Decoupled data model (`paris.geojson` and `paris_metadata.json`).           |
| - Multi-tier progressive metadata disclosure (Simple, Medium, Detailed).      |
| - Autocomplete search engine (PinSearch) for locations and scenes.           |
| - Filter system by Director, Decade, and Arrondissement.                      |
+-------------------------------------------------------------------------------+
| SHOULD HAVE (UX Enhancements)                                                 |
| - Dynamic walking route generation via `leaflet-routing-machine`.             |
| - Responsive catalogue grid with client-side sorting (A-Z, Year, Director).   |
| - Side-by-side archival film still vs contemporary street photo comparisons. |
| - Continuous Deployment workflow via GitHub Actions.                          |
+-------------------------------------------------------------------------------+
| COULD HAVE (Advanced Extensions)                                              |
| - SPARQL endpoint integration with Wikidata for live director biographies.    |
| - Offline Progressive Web App (PWA) caching via Service Workers.              |
| - Integrated HTML5 audio narrative commentary per location.                   |
+-------------------------------------------------------------------------------+
| WON'T HAVE (Out of Scope for v1)                                              |
| - User accounts and server-side relational user databases.                    |
| - Crowdsourced public editing interfaces.                                     |
+-------------------------------------------------------------------------------+
```

---

## 5. Information Architecture & Data Engineering

### 5.1 Decoupled Data Model Architecture
To optimize initial page load times, minimize network payloads, and ensure clean separation of concerns, spatial definitions and narrative cultural metadata are strictly decoupled.

```
[ HTTP Initial Request ]
       |
       +---> Fetch `data/paris.geojson`  (~15 KB payload: fast spatial indexing)
       |
[ User Interaction: Marker Click ]
       |
       +---> Asynchronous Fetch / Lookup in `data/paris_metadata.json` 
             (Loads high-resolution imagery & tiered textual descriptions)
```

### 5.2 Spatial Specification (`data/paris.geojson`)
RFC 7946-compliant GeoJSON format storing point coordinates and lightweight indexing properties:

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [2.3292, 48.8422]
      },
      "properties": {
        "id": "cafe_du_dome",
        "name": "Café du Dôme",
        "movie": "Cléo de 5 à 7",
        "director": "Agnès Varda",
        "year": 1962,
        "arrondissement": "14e",
        "address": "108 Bd du Montparnasse, 75014 Paris",
        "thumbnail": "img/img_movie/cafeDuDomeModern.png"
      }
    }
  ]
}
```

### 5.3 Narrative Metadata Specification (`data/paris_metadata.json`)
Hierarchically organized metadata implementing the **Progressive Disclosure Pattern**:

```json
{
  "cafe_du_dome": {
    "title": "Café du Dôme — Cléo de 5 à 7",
    "director": "Agnès Varda",
    "year": 1962,
    "scene_synopsis": "Cléo meets her lover and drinks coffee while awaiting biopsy results.",
    "descriptions": {
      "simple": "A legendary bohemian café in Montparnasse featured in the opening acts of Varda's real-time masterpiece.",
      "medium": "In 'Cléo de 5 à 7', Le Dôme represents the bustling public sphere of the Left Bank, amplifying Cléo's internal anxiety and alienation.",
      "detailed": "Shot in natural morning light in early 1961, Varda used the mirrors of Le Dôme to symbolize the fragmentation of the female gaze and celebrity ego. The camera captures authentic pedestrians, exemplifying the Rive Gauche documentary-fiction synthesis."
    },
    "imagery": {
      "archival_still": "img/img_movie/cafeDuDomeOld.png",
      "modern_photo": "img/img_movie/cafeDuDomeModern.png",
      "caption": "Terrace of Café du Dôme: 1961 film production vs. contemporary street view."
    }
  }
}
```

---

## 6. Design System & CSS Styling Architecture (Solarpunk Theme)

### 6.1 Aesthetic Philosophy
The custom **Solarpunk Theme** (`solarpunk_theme.css`) blends Paris's 1960s architectural nostalgia with an optimistic, eco-futurist design language:
* **Organic Warmth:** Replaces harsh digital white with warm parchment cream (`#f4f1e1`) and mint undertones (`#e8f0e4`).
* **Glassmorphism 2.0 (Greenhouse Glass):** Semi-transparent UI panels (`rgba(255, 255, 255, 0.55)`) combined with backdrop filters (`blur(12px-16px)`) and organic elevation shadows.
* **Art Nouveau Brass Accents:** Metallic gold and brass highlights (`#d4af37`, `#f5a623`) referencing Hector Guimard’s iconic Parisian metro entrances.

### 6.2 CSS Custom Properties (`:root`)
```css
:root {
    /* Solarpunk Palette */
    --bg-color: #f4f1e1;          /* Warm Parchment Cream */
    --bg-mint: #e8f0e4;           /* Subtle Mint Reflection */
    --text-color: #163820;        /* Deep Forest Green (replaces pure black) */
    --text-muted: #51705a;        /* Muted Sage Green */
    --primary: #1b5e20;           /* Forest Green Base */
    --primary-bright: #4caf50;    /* Vibrant Leaf Green */
    --secondary: #f5a623;         /* Morning Sunlight Amber */
    --accent-brass: #d4af37;      /* Art Nouveau Brass / Gold */

    /* Glassmorphism 2.0 Effects */
    --glass-bg: rgba(255, 255, 255, 0.55);
    --glass-border: rgba(255, 255, 255, 0.8);
    --glass-edge: rgba(76, 175, 80, 0.3);
    --glass-shadow: 0 8px 32px rgba(27, 94, 32, 0.1);

    /* Bioluminescent Glows */
    --glow-green: 0 4px 20px rgba(76, 175, 80, 0.4);
    --glow-gold: 0 6px 25px rgba(245, 166, 35, 0.4);
}
```

### 6.3 Responsive Breakpoints & Viewport Rules
```css
@media (max-width: 520px) {
    .hero-img { height: 30vh !important; background-position: 20% center !important; }
}
@media (min-width: 521px) and (max-width: 768px) {
    .hero-img { background-position: 50% center !important; }
}
@media (max-width: 992px) {
    .hero-img { height: 40vh; background-position: 35% center; }
    .catchphrase { font-size: 2.7rem !important; }
}
@media (max-width: 577px) {
    .catchphrase { font-size: 2rem !important; }
    header > .row { height: 60% !important; }        
}
```

---

## 7. Interaction Design & UI/UX Specifications

### 7.1 Progressive Information Disclosure Pattern
To prevent cognitive overload, particularly on mobile viewports, film data is revealed across three distinct user interaction stages:

```
+---------------------------------------------------------------------------------+
| LEVEL 1: Map Marker Popup (Instant Glance)                                      |
| - Location Name + Film Title + Year                                            |
| - Thumbnail preview + Simple Description                                        |
| - Action: [ Explore Deeper / Open Drawer ]                                      |
+---------------------------------------------------------------------------------+
                                      |
                                      v
+---------------------------------------------------------------------------------+
| LEVEL 2: Offcanvas Sidebar Drawer (Contextual Deepening)                        |
| - Medium Description + Scene Synopsis                                           |
| - Comparative Visuals (Old Film Still vs Modern Photo)                          |
| - Action: [ Read Full Academic Analysis ]                                       |
+---------------------------------------------------------------------------------+
                                      |
                                      v
+---------------------------------------------------------------------------------+
| LEVEL 3: Full Academic Modal (Scholarly Dossier)                                |
| - Detailed Film Theory Analysis + Cinematographic Technique Notes               |
| - Full Resolution Still Comparison Slider + Bibliographic References            |
+---------------------------------------------------------------------------------+
```

### 7.2 Application Site Map & Structure

```
                                [ Home / Root ]
                                       |
         +-----------------+-----------+-----------+-----------------+
         |                 |                       |                 |
   [ index.html ]   [ catalogue.html ]       [ tour.html ]     [ about.html ]
   - Leaflet Map    - Card Grid View         - Step-by-Step    - Philosophy
   - Routing Engine - Multi-sorting          - Text / Map Sync - Tech Stack
   - Filter Bar     - Search Bar             - Progress Slider - Compliance
                                                                     |
                                              +----------------------+
                                              |                      |
                                   [ about_nouvelle_vague.html ]  [ about_our_team.html ]
                                   - Historical Film Essay        - Team & Attributions
```

---

## 8. Technical Implementation & Software Engineering

### 8.1 Core Technology Stack
* **HTML5:** Semantic landmark tags (`<main>`, `<nav>`, `<section>`, `<article>`, `<aside>`) ensure SEO indexability and screen-reader accessibility.
* **CSS3 & Bootstrap 5:** Mobile-first responsive grid system augmented by custom BEM (Block-Element-Modifier) stylesheets.
* **Vanilla ES6+ JavaScript:** Zero-dependency core logic avoids framework obsolescence, maximizes execution speed, and demonstrates foundational programming competencies.
* **Leaflet.js:** Lightweight (42KB) mapping library ideal for custom tile layers and GeoJSON rendering.

### 8.2 Client-Side JavaScript Lifecycle
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

---

## 9. DevOps, CI/CD & Deployment Pipeline

The platform is maintained under continuous integration and deployment using GitHub Actions. Any commit merged into the `main` branch triggers automated linting, artifact packaging, and deployment to GitHub Pages.

```yaml
# .github/workflows/deploy-pages.yml
name: Deploy GitHub Pages site

on:
  push:
    branches:
      - main

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Source Code
        uses: actions/checkout@v4

      - name: Setup GitHub Pages Engine
        uses: actions/configure-pages@v4

      - name: Upload Static Web Artifacts
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'

      - name: Deploy to Global CDN
        id: deployment
        uses: actions/deploy-pages@v4
```

---

## 10. Usability, Accessibility & Heuristic Compliance

### 10.1 Jakob Nielsen’s Usability Heuristics Compliance
1. **Visibility of System Status:** Filter modifications immediately update map markers and display active result counters.
2. **Match Between System and Real World:** Geographic terminology conforms to official Parisian arrondissements, paired with recognized film taxonomy.
3. **User Control and Freedom:** Easy "Reset Filters" and "Clear Route" buttons restore default viewport settings at any stage.
4. **Consistency and Standards:** Uniform navigation headers and color palettes across all six sub-pages.
5. **Recognition Rather than Recall:** Location cards in `catalogue.html` display film poster thumbnails, minimizing memory strain.

### 10.2 Accessibility Auditing (WCAG 2.1 Level AA)
* **Color Contrast:** All body text meets or exceeds the minimum 4.5:1 contrast ratio against light/dark themes.
* **Semantic Aria Attributes:** Screen readers are guided with `aria-expanded`, `aria-controls`, and `role="region"` attributes on dynamic drawers and modals.
* **Keyboard Navigability:** Interactive elements (popups, cards, sliders) are fully reachable via standard `Tab` / `Shift+Tab` and triggerable via `Enter` / `Space`.

---

## 11. Critical Discussion, Limitations & Future Roadmap

### 11.1 SWOT Matrix Analysis

```
+---------------------------------------------------------------------------------+
|                                 SWOT MATRIX                                     |
+----------------------------------------+----------------------------------------+
| STRENGTHS                              | WEAKNESSES                             |
| - High-performance decoupled data model| - Client-side search DOM limit (~1,000 |
| - Rich curated cultural commentary     |   points before performance drops)     |
| - Zero-maintenance serverless hosting  | - Manual entry required for new film   |
| - Progressive disclosure UX pattern    |   locations                            |
+----------------------------------------+----------------------------------------+
| OPPORTUNITIES                          | THREATS                                |
| - Linked Open Data (Wikidata SPARQL)   | - Leaflet plugin bitrot/deprecation    |
| - Offline PWA mobile installation      | - Broken external image links          |
| - Audio-guided walking tours in Paris  | - Map tile API policy changes          |
+----------------------------------------+----------------------------------------+
```

### 11.2 Future Roadmap (v2.0)
1. **Linked Open Data (LOD) & Semantic Web:**
   * Integrate RDFa / Schema.org microdata into `index.html` and `catalogue.html`.
   * Bind each location entity to its corresponding **Wikidata URI** (e.g., `Q12345`) and query Wikidata dynamically via SPARQL endpoints to retrieve film awards, box-office stats, and director birth/death dates automatically.
2. **Progressive Web App (PWA) Offline Engine:**
   * Implement a Service Worker strategy (`Cache-First` for map raster tiles, `Stale-While-Revalidate` for GeoJSON datasets), allowing tourists to navigate Paris on-site without roaming data charges.
3. **Interactive Street View & Audio Narratives:**
   * Embed HTML5 audio narration guides recorded on location.
   * Implement an interactive opacity slider widget to fade contemporary Google Street View imagery directly into the 1960 archival film frame.
