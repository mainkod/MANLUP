Baik Rahman Sha.
Di bawah ini ialah versi **README Technical Heavy (Developer-Focused)** untuk GitHub MANLUP.

Struktur ini lebih sesuai untuk dev, contributor, dan enterprise integrator.

---

# 🧠 MANLUP

## Man Neutral Language Understanding Engine

**Deterministic • Offline • Dataset-Driven • Audit-Ready**

---

## Overview

**MANLUP** is a lightweight, deterministic Natural Language Understanding (NLU) engine built with pure Node.js.

It is designed for:

* Offline-first chatbot systems
* SME business automation
* Embedded AI devices
* Controlled enterprise environments

MANLUP does **not** rely on external APIs or cloud LLM services.

---

## Design Philosophy

MANLUP follows strict architectural principles:

* No external runtime dependencies
* No cloud calls
* No hidden AI logic
* No probabilistic hallucination
* Fully dataset-driven behavior
* Deterministic response pipeline

---

## Core Architecture

Returns:

```json
{
  "rawText": "...",
  "normalizedText": "...",
  "normalizeChanged": true,
  "normalizeConfidence": 0.92,
  "corrections": [...]
}
```

---

### 2. ISA (Intent Signature Analysis)

ISA is MANLUP’s deterministic pattern detection engine.

Components:

* Anchor detection
* Token class mapping
* Pattern signature matching
* DomainGuard isolation
* Context-aware overrides

ISA has priority over probabilistic scoring.

---

### 3. Hybrid Probabilistic Layer

Lightweight Naive Bayes classifier used as fallback scoring.

Purpose:

* Rank potential intents
* Provide confidence metrics
* Resolve ambiguous patterns

Deterministic override always wins.

---

### 4. Context Manager

Handles multi-turn conversation:

* Required slot tracking
* Slot prompting
* Action triggers
* Follow-up chaining
* Conversation state control

---

## Data-Driven Architecture

MANLUP behavior is fully controlled by JSON datasets.

Example structure:

```
/DATA
  /PACKS
    /DEFAULT
      /INTENTS
      /SIGNATURES
      /RULES
      /CHAINS
      /TRAINING
```

No intent logic is hardcoded inside the engine.

---

## Example Intent Schema

```json

---

## API Contract (v1/chat)

MANLUP returns structured evidence:

```json
{
  "intent": "TCR.AVAILABILITY.ROOM",
  "confidence": 0.94,
  "slots": {
    "pax": 4
  },
  "normalizeEvidence": {
    "normalizeChanged": true
  }
}
```

Audit-friendly by design.

---

## Runtime Modes

### CLI Mode

Interactive local testing.

### API Mode

REST endpoint:

```
POST /v1/chat
```

### Embedded Mode

Import MANLUP engine inside another Node.js application.

---

## Performance Characteristics

* Ultra-light memory footprint
* No ML model loading
* No GPU dependency
* Fast startup (< 100ms typical)
* Stable under SME workload

---

## Security Model

* No external network calls
* No hidden inference
* Fully inspectable logic
* Controlled fallback mechanism

---

## Use Cases

### SME Chatbot Engine

* WhatsApp automation
* Telegram bot integration
* Booking systems

### CRM Workflow Engine

* Lead qualification
* Ticket routing
* Case escalation

### Offline AI Device

* AI box
* On-premise deployment
* Secure enterprise internal system

---

## Comparison

| Feature            | MANLUP     | LLM      |
| ------------------ | ---------- | -------- |
| Offline            | Yes        | No       |
| Deterministic      | Yes        | No       |
| Hallucination Risk | None       | Possible |
| Audit Trail        | Structured | Limited  |
| Cloud Required     | No         | Yes      |

MANLUP can act as a control layer before LLM escalation.

---

## Roadmap

### v3.x

* ISA-FULL core spec
* Hybrid scoring stable
* Dataset normalization governance

### v4.x

* Modular engine architecture
* Pack isolation enforcement
* DomainGuard enhancement

### v5.x

* Enterprise audit tools
* Advanced token class expansion
* Cross-domain orchestration

---

## License

MANLUP Custom License (2025)
Powered by MANLUP
Copyright (c) 2025 Abdul Rahman Sha

Commercial use requires written license.

---

## Contribution Policy

MANLUP follows:

* SPEC-first development
* No code without architectural approval
* Deterministic-first enforcement
* Dataset-driven evolution

---

## Author

Abdul Rahman Sha | a.rahmansha@gmail.com
Founder & Architect of MANLUP 2021-2025
