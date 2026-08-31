# 4. Functional & Non-Functional Requirements (MoSCoW Matrix)

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