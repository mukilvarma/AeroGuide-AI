# ADR-001: Selection of POI (Places) Data Provider

**Status:** Accepted  
**Date:** 2026-01-31

---

## Context

AeroGuide AI requires reliable and up-to-date information about airport points of interest (POIs) such as restaurants, cafes, lounges, restrooms, and pharmacies.  
The POI data must support international airports and provide reasonable accuracy inside terminals.

---

## Options Considered

1. Google Places API  
2. HERE Places API  
3. OpenStreetMap (OSM)

---

## Decision

Use **Google Places API** as the initial POI data provider for the MVP.

---

## Rationale

- Strong global coverage for major international airports
- Better quality data for airport restaurants and retail
- Supports metadata such as opening hours and place identifiers
- Faster integration for an MVP

---

## Consequences

- API usage cost at scale
- Restrictions on long-term caching of place details
- Architecture must allow provider replacement via adapter pattern

---

## Notes

The POI provider is abstracted behind a `POI Adapter` to allow future migration if needed.
