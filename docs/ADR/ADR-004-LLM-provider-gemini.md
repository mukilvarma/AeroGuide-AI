# ADR-004: Selection of LLM Provider using Google Gemini Files API

**Status:** Accepted  
**Date:** 2026-01-31

---

## Context

AeroGuide AI requires a Large Language Model (LLM) to:
- Understand user intent
- Reason over retrieved RAG context
- Generate multilingual, natural-language responses

The LLM is accessed as an external API and is not self-hosted.

---

## Options Considered

1. OpenAI API (GPT models)
2. Azure OpenAI Service
3. Google Gemini API (Files API)

---

## Decision

Use **Google Gemini Files API** as the initial LLM provider for development and early-stage usage.

---

## Rationale

- Google Gemini Files API currently offers **free usage suitable for development**
- Strong multilingual capabilities
- Integrates well with other Google services already used in the system
- Supports rapid prototyping without upfront cost
- External API model aligns with the system’s architecture

---

## Consequences

- Free usage is subject to change based on Google’s pricing policy
- System must be designed to allow easy LLM provider replacement
- Production deployment may require switching to a paid tier or alternate provider

---

## Mitigations

- LLM access is abstracted behind an `LLM Client` interface
- Prompts and response handling are provider-agnostic
- Future providers (OpenAI, Azure OpenAI) can be plugged in with minimal changes

---

## Notes

This decision applies to **development and early demos only**.  
Production deployment will re-evaluate the LLM provider based on cost, latency, and compliance requirements.
