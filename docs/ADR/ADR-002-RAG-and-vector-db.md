# ADR-002: Use of RAG with Vector Database

**Status:** Accepted  
**Date:** 2026-01-31

---

## Context

AeroGuide AI must provide accurate, airport-specific answers such as:
- Nearest restroom from a gate
- Reachable food options before boarding
- Airport transfer rules

A generic LLM does not have knowledge of airport layouts, curated POIs, or local rules.

---

## Options Considered

1. LLM-only responses without retrieval  
2. Traditional database queries only  
3. Retrieval-Augmented Generation (RAG) using a Vector Database

---

## Decision

Adopt **Retrieval-Augmented Generation (RAG)** backed by a **Vector Database**.

---

## Rationale

- Grounds AI responses in real, project-owned airport data
- Enables semantic and multilingual search
- Reduces hallucinations by forcing answers to use retrieved context
- Supports future personalization and similarity-based recommendations

---

## Consequences

- Additional infrastructure component (vector storage)
- Slight increase in system complexity
- Clear separation between retrieval and generation responsibilities

---

## Notes

Vector search complements structured databases and does not replace them.
