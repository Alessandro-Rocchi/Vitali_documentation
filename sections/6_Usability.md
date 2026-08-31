# 6. Interaction Design & UI/UX Specifications

## 6.1 Progressive Information Disclosure Pattern
To prevent cognitive overload on mobile devices and small viewports, information is presented in three escalating tiers:

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
6.2 Application Sitemap & Page Hierarchy
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