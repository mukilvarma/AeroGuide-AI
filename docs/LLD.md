# HLD — AeroGuide AI
## Multilingual, Voice-First AI Transit Assistant for Airports

---

## 1. Problem Statement
Modern international airports are complex transit hubs where passengers frequently struggle to find relevant services within limited time windows.

### Passenger Challenges
- Difficulty identifying what is nearby from their current gate
- Language barriers while navigating food options, facilities, and rules
- Uncertainty about what can be reached before boarding
- Existing airport apps are static, map-heavy, and not conversational

### Operational Gaps
- Information is scattered across displays, maps, and websites
- No unified system combines location, time, preferences, and language
- Human help desks do not scale during peak transit hours

---

## 2. Proposed Solution
AeroGuide AI is a voice-first, multilingual, AI-powered transit assistant that helps passengers discover nearby facilities and services and guides them accurately based on their time, preferences, and location.

---

## 3. Key Capabilities

### 3.1 Location & Time Awareness
- Terminal and gate-based context
- Boarding-time aware filtering
- Recommendations limited to reachable options

### 3.2 Multilingual Voice & Chat
- Automatic language detection
- Natural voice interaction
- Responses delivered in the passenger’s preferred language

### 3.3 Intelligent Recommendations
- Food, coffee, lounges, restrooms, pharmacies
- Dietary preferences (vegetarian, halal, etc.)
- Budget and crowd sensitivity
- Optional personalization from past interactions

### 3.4 Grounded Responses using RAG
- Answers generated only from real airport data
- No hallucination or guessing
- Safe fallbacks when data is unavailable

---

## 4. Why RAG (Retrieval-Augmented Generation)
Generic AI models lack airport-specific knowledge.

RAG ensures:
- Relevant airport knowledge is retrieved
- The AI answers using retrieved facts
- Responses remain accurate and trustworthy

---

## 5. Why Vector Database
Passengers communicate using intent, not structured queries.

Examples:
- “Something quick and quiet”
- “Light food near me”
- “I liked that place last time”

A vector database enables:
- Semantic (meaning-based) search
- Multilingual understanding
- Preference-based personalization

---

## 6. High-Level Architecture

```mermaid
flowchart TB
  App[Mobile App / PWA] --> API[API Gateway]

  API --> Ctx[Trip Context Service]
  API --> Chat[Chat Orchestrator]
  API --> Rec[Recommendation Service]

  Chat --> STT[Speech-to-Text]
  Chat --> LLM[LLM Provider\nOpenAI/Gemini]
  Chat --> Lang[Language Service]
  Chat --> Trans[Translation Adapter\n(optional)]

  Rec --> POI[POI Provider Adapter\nGoogle/HERE/OSM]
  Rec --> Route[Routing Adapter\nGoogle Routes]
  Rec --> DB[(Postgres)]
  Rec --> VDB[(Vector DB)]
  Rec --> Cache[(Redis Cache)]
