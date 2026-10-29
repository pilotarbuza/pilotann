# Project Roadmap — ANN (pilotann)

[ English | [Русский](ROADMAP.ru.md) ]

This document outlines the strategic development milestones of the **ANN** aviation platform, tracking current production capabilities and planned releases.

---

## Current Status: Version 1.2 (Active Production)

The aviation RAG engine is deployed and operational in production across the Telegram Bot and PWA client.

### Implemented Capabilities:
- **Hybrid RAG Engine**: Blended SQLite FTS5 (BM25) and LanceDB (`multilingual-e5-base`) via Reciprocal Rank Fusion ($k=60$).
- **Dual-Stage Answer Verification**: Immediate drafting via Claude Haiku followed by strict numerical verification via Claude Sonnet.
- **Visual Page Citations**: Dynamic PDF page rasterization using `pypdfium2` with coordinate bounding-box sentence highlighting.
- **Fleet Coverage**: Airbus (A220–A380), Boeing (737–787), Superjet 100, ATR 42/72, Embraer, CRJ, Dash 8, L-410, Cessna, Diamond.
- **Aviation Weather**: Real-time METAR / TAF tokenizer with runway-specific crosswind and headwind calculations.
- **SimBrief Integration**: Operational Flight Plan (OFP) XML/JSON parser with fuel, ZFW, route, and alternate aerodrome calculations.
- **Telegram Mini App & PWA**: Production web client at `ann.pilotarbuza.com` supporting Telegram, Google, Apple ID, and Email authentication.
- **Aviation Regulations**: Built-in indexed search across ICAO Annexes, FAA regulations, and Russian Federal Aviation Rules (FAP 128, 293, 10, 147).

---

## Near-Term Milestones (Q1–Q2 2027)

### 1. Knowledge Base & Fleet Expansion
- [ ] Integration of complete Normal Checklists and Non-Normal Checklists (QRH) with step-by-step interactive pilot guidance.
- [ ] Minimum Equipment List (MEL) reasoning engine with automated calculation of defect deferral conditions (Rectification Interval Categories A, B, C, D).
- [ ] Optimized chunking and tabular parsing for aircraft performance tables (Takeoff/Landing Distances, Engine-Out climb gradients).

### 2. Client & PWA Enhancements
- [ ] Interactive flight route map: display of enroute alternate aerodromes along SimBrief flight tracks with color-coded weather flight categories (VFR / MVFR / IFR / LIFR).
- [ ] Offline caching for emergency checklists via IndexedDB and Service Worker in the PWA.
- [ ] Cross-platform synchronization of bookmarks and query history between Telegram and Web clients.

---

## Long-Term Vision (Q3–Q4 2027)

### 3. Voice Input & Aviation Phraseology
- [ ] Speech-to-text integration (Whisper) fine-tuned on standard ICAO radio telephony phraseology (Doc 9432).
- [ ] Rapid verbal parameter entry (*"Vnukovo weather runway 19 wind"*) with instant speech or text synthesis.

### 4. On-Device Local Inference (Offline Flight Deck Mode)
- [ ] WebAssembly / ONNX Runtime Web deployment of lightweight embedding models running directly inside the pilot's browser (PWA) for cruise flight with zero connectivity.
- [ ] Local search against pre-cached operator manuals on pilot Electronic Flight Bag (EFB) devices.
