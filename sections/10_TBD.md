# 10. Critical Discussion, Limitations & Future Roadmap

## 10.1 SWOT Matrix Analysis

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

## 10.2 Future Roadmap (v2.0)

1. **Linked Open Data (LOD) & Semantic Web:**
   * Integrate RDFa / Schema.org microdata into `index.html` and `catalogue.html`.
   * Bind each location entity to its corresponding **Wikidata URI** (e.g., `Q12345`) and query Wikidata dynamically via SPARQL endpoints to retrieve film awards, box-office stats, and director birth/death dates automatically.
2. **Progressive Web App (PWA) Offline Engine:**
   * Implement a Service Worker strategy (`Cache-First` for map raster tiles, `Stale-While-Revalidate` for GeoJSON datasets), allowing tourists to navigate Paris on-site without roaming data charges.
3. **Interactive Street View & Audio Narratives:**
   * Embed HTML5 audio narration guides recorded on location.
   * Implement an interactive opacity slider widget to fade contemporary Google Street View imagery directly into the 1960 archival film frame.
