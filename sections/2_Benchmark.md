# 2. Benchmark & User Personas

## 2.1 Benchmark

Before defining the application's architecture, we analyzed existing solutions in the realms of cinematic tourism and urban exploration:

* **Generic Movie Location Databases (e.g., IMDb Locations, MovieLocations.com):**
  * *Limitations:* These are usually extensive text-based databases or simple photo galleries. They lack an advanced, interactive cartographic interface, offer no curated focus on a single movement (like the Nouvelle Vague), and do not generate walkable routes.

* **Standard Navigation Apps (e.g., Google Maps):**
  * *Limitations:* While exceptional for calculating routes, they lack a dedicated cultural and narrative layer. Historical cinematic landmarks get completely lost among millions of generic commercial activities.
  
* **Traditional Tourist Guides (Print or Apps):**
  * *Limitations:* Print guides lack dynamic, real-time geolocation. Generic tourism apps rarely offer highly specific cinematic filters (e.g., filtering a city walk exclusively by "Director" or "Production Year").

| Dimension / Feature | IMDb Locations | Google Maps / Earth | Movie-Locations.com | **Les Rues du CSS** (Ours) |
| :--- | :--- | :--- | :--- | :--- |
| **Spatial Interactivity** | None (Flat text list) | High (Generic maps) | Low (Static map embed) | **High (Custom Leaflet Canvas)** |
| **Thematic Focus** | Global (Unfiltered) | Commercial POIs | General Cinema | **Specialized Nouvelle Vague** |
| **Progressive Disclosure** | None | None | None | **3-Tier Dynamic Loading** |
| **Topological Routing** | None | Generic Navigation | None | **Dynamic Walking Tour Engine** |
| **Comparative Imagery** | User photos (loose) | User Street View | Film stills only | **Curated Archival vs. Modern Stills**|
| **Data Decoupling** | Monolithic DB | Monolithic DB | Server-side CMS | **Decoupled GeoJSON + JSON Meta** |

**Our Unique Selling Proposition (USP):**
Unlike existing competitors, *Les Rues du CSS* merges a highly specialized, curated database with advanced geographic interactivity. Instead of merely displaying disconnected points of interest, the platform actively links places and aesthetics. It offers granular filters (by author, by decade) and dynamically traces itineraries (using routing algorithms) to let users physically walk the sets of the French New Wave.

## 2.2 User Personas & Scenarios

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