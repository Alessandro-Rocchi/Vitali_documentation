# 1. The Idea & Core Concept

## 1.1 Abstract

**Les Rues du CSS** is an interactive web application designed to allow users to explore the city of Paris through the historical and aesthetic lens of the **Nouvelle Vague** (New Wave) cinema.

The fundamental concept revolves around a bidirectional cinematic cartography:

* **From Location to Film:** Every physical location on the map is directly linked to the specific movie scene that was shot there.

* **From Film to Location:** Every movie or director acts as a thematic guide to discovering the real, physical topography of Paris.

During the late 1950s and 1960s, Nouvelle Vague directors (such as Jean-Luc Godard, François Truffaut, Agnès Varda, and Éric Rohmer) famously abandoned traditional sound stages. They took to the streets with lightweight cameras and natural lighting, transforming the city of Paris from a mere decorative backdrop into a breathing, active character in their narratives. This project aims to capture that essence, allowing users to physically or virtually trace the footsteps of these cinematic pioneers.

By combining modern web mapping engines (Leaflet.js), dynamic routing calculation, progressive information disclosure, and decoupled spatial-semantic data storage, the application serves both academic film scholars and cultural flâneurs seeking to experience cinema through space.

### 1.2 Research Questions & Core Objectives

* **Research Question:** *How can interactive web mapping methodologies reconstruct the symbiotic relationship between urban spatial realism and the revolutionary filmmaking practices of the Nouvelle Vague?*
* **Primary Educational & Technical Objectives:**
  * Implement a zero-backend, high-performance client-side application using vanilla JavaScript and standards-compliant HTML5/CSS3.
  * Establish an optimized, decoupled data model separating pure GeoJSON spatial features from rich cultural and comparative visual metadata.
  * Deliver an accessible, responsive user experience optimized for walking navigation and desktop scholarly research.
