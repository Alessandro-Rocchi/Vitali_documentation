# 5. Information Architecture & Data Engineering

## 5.1 Decoupled Data Model Architecture

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
