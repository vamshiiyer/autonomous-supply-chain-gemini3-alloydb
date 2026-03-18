# 🤖 Autonomous Supply Chain Agent
### Gemini 3 Flash · AlloyDB ScaNN · A2A Protocol

> **Built by Vamshi Krishna ** as part of [Code Vipassana Season 14](https://www.codevipassana.dev/) — a hands-on exploration of Deterministic AI Engineering for real-world supply chain automation.

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Gemini](https://img.shields.io/badge/Gemini_3_Flash-AI_Vision-4285F4?style=flat-square&logo=google&logoColor=white)](https://ai.google.dev)
[![AlloyDB](https://img.shields.io/badge/AlloyDB-ScaNN_Vector_Search-DB4437?style=flat-square&logo=google-cloud&logoColor=white)](https://cloud.google.com/alloydb)
[![License](https://img.shields.io/badge/License-Apache_2.0-green?style=flat-square)](LICENSE)

---

## 🧠 What I Built

A **multi-agent autonomous supply chain system** that eliminates guesswork from warehouse management. Standard AI models hallucinate counts from images — a dangerous flaw in supply chains. This system solves that with **Deterministic AI Engineering**: instead of predicting tokens, the model writes and executes Python (OpenCV) to count items with mathematical precision.

### The Three Pillars

| Agent | Technology | Role |
|-------|-----------|------|
| 👁️ **Vision Agent** | Gemini 3 Flash + Code Execution | Counts inventory items deterministically via OpenCV |
| 🧠 **Supplier Agent** | AlloyDB AI + ScaNN | Finds the right supplier from millions of parts in milliseconds |
| 🗼 **Control Tower** | FastAPI + WebSockets | Orchestrates the full pipeline with real-time updates |

---

## 🏗️ Architecture
```
Camera Feed / Image Upload
        │
        ▼
┌──────────────────┐     A2A Protocol      ┌──────────────────────┐
│   Vision Agent   │ ──────────────────▶  │   Supplier Agent     │
│                  │                       │                      │
│ Gemini 3 Flash   │   "14 cardboard       │ AlloyDB ScaNN        │
│ + Code Execution │    boxes detected"    │ Vector Search        │
│ (OpenCV counts)  │                       │ (text-embedding-005) │
└──────────────────┘                       └──────────────────────┘
        │                                           │
        └──────────────┬────────────────────────────┘
                       ▼
            ┌─────────────────────┐
            │   Control Tower     │
            │  FastAPI WebSocket  │
            │  Real-time UI       │
            └─────────────────────┘
                       │
                       ▼
              ✅ Order Placed Autonomously
```

---

## 🚀 Key Technical Decisions

### Why Code Execution over Standard Vision?
Standard multimodal models guess counts. Gemini 3 Flash with Code Execution writes Python → runs OpenCV → returns an exact integer. No hallucinations. **Deterministic output.**

### Why ScaNN over HNSW?
| Metric | HNSW (pgvector) | ScaNN (AlloyDB) |
|--------|----------------|-----------------|
| Filtered search speed | Baseline | **10x faster** |
| Standard search speed | Baseline | **4x faster** |
| Memory footprint | Baseline | **3-4x smaller** |
| Index build time | Baseline | **8x faster** |

### Why A2A Protocol?
Dynamic discovery via `/.well-known/agent-card.json` — add a new agent and the Control Tower finds it automatically. Zero config. Plug-and-play.

---

## 🛠️ Tech Stack

- **AI/ML**: Gemini 3 Flash (MINIMAL thinking + Code Execution), Vertex AI text-embedding-005
- **Database**: AlloyDB for PostgreSQL with ScaNN vector index
- **Backend**: FastAPI, WebSockets, AlloyDB Python Connector
- **Protocol**: A2A (Agent-to-Agent) for agent discovery and communication
- **Infrastructure**: Google Cloud (Cloud Shell, Cloud Run, Vertex AI)

---

## ⚡ Quick Start
```bash
git clone https://github.com/vamshiiyer/autonomous-supply-chain-gemini3-alloydb.git
cd autonomous-supply-chain-gemini3-alloydb
sh setup.sh
sh run.sh
```

Open [http://localhost:8080](http://localhost:8080) → upload a warehouse image → watch the autonomous pipeline run.

---

## 📚 References

- [Gemini 3 Flash — Code Execution API](https://cloud.google.com/vertex-ai/generative-ai/docs/model-reference/code-execution-api)
- [AlloyDB ScaNN vs HNSW Benchmarks](https://cloud.google.com/blog/products/databases/how-scann-for-alloydb-vector-search-compares-to-pgvector-hnsw)
- [A2A Protocol](https://agent2agent.info/)
- [Code Vipassana Season 14](https://www.codevipassana.dev/)

---

## 👤 Author

Ayyavari Vamshi Krishna — Built this as part of Code Vipassana Season 14.

> *"The era of chatbots that read is ending. We are entering the era of Agentic Vision."*

---
<p align="center">
  <sub>Powered by Gemini 3 Flash · AlloyDB AI · A2A Protocol · Google Cloud</sub>
</p>
