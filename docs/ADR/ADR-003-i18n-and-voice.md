# ADR-003: Multilingual and Voice-First Interaction Model

**Status:** Accepted  
**Date:** 2026-01-31

---

## Context

Airport transit passengers are often:
- Multilingual
- Time-constrained
- Physically mobile (walking, carrying luggage)

Typing on a mobile device is inconvenient, and English-only interfaces exclude many users.

---

## Options Considered

1. English-only, text-based interaction  
2. Multilingual UI with text input only  
3. Multilingual, voice-first interaction with text fallback

---

## Decision

Implement a **multilingual, voice-first interaction model** with automatic language detection.

---

## Rationale

- Voice interaction is faster and hands-free
- Automatic language detection reduces user friction
- Improves accessibility for non-English speakers
- Matches the global nature of international airports

---

## Consequences

- Dependency on Speech-to-Text services
- Need for a Language Resolution Service
- Additional testing for accents and multiple languages

---

## Notes

Text input remains available as a fallback when voice is not practical.
