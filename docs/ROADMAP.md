# ANN roadmap

[ English | [Русский](ROADMAP.ru.md) ]

What ANN can do today and what comes next.

## Now: version 1.2, in production

The search engine runs in production behind the Telegram bot and the PWA.

What already works:

- Hybrid search: SQLite FTS5 (BM25) and LanceDB (`multilingual-e5-base`) merged with Reciprocal Rank Fusion ($k=60$).
- Two-step answers: Claude Haiku writes a quick draft, then Claude Sonnet checks every number against the source.
- Page citations: `pypdfium2` renders the PDF page and the quoted sentence is highlighted by its bounding box.
- Aircraft: Airbus (A220–A380), Boeing (737–787), Superjet 100, ATR 42/72, Embraer, CRJ, Dash 8, L-410, Cessna, Diamond.
- Weather: a live METAR and TAF parser that works out crosswind and headwind for each runway.
- SimBrief: parses the flight plan (OFP) in XML or JSON, including fuel, ZFW, route and alternates.
- Telegram Mini App and PWA at `ann.pilotarbuza.com`, with sign-in through Telegram, Google, Apple ID or email.
- Regulations: indexed search over ICAO Annexes, FAA regulations and the Russian Federal Aviation Rules (FAP 128, 293, 10, 147).

## Next: Q1–Q2 2027

### Manuals and aircraft

- [ ] Full Normal and Non-Normal checklists (QRH), walked through step by step.
- [ ] MEL support that works out when a defect can be deferred (rectification interval categories A, B, C, D).
- [ ] Better chunking and table parsing for performance data: takeoff and landing distances, engine-out climb gradients.

### Mini App and PWA

- [ ] A route map that shows en-route alternates along the SimBrief track, colored by flight category (VFR, MVFR, IFR, LIFR).
- [ ] Emergency checklists available offline in the PWA through IndexedDB and a service worker.
- [ ] Bookmarks and query history synced between the bot and the web app.

## Later: Q3–Q4 2027

### Voice input

- [ ] Speech recognition with Whisper, fine-tuned on standard ICAO radiotelephony phraseology (Doc 9432).
- [ ] Asking by voice (*"Vnukovo weather runway 19 wind"*) and getting the answer back as speech or text.

### Offline mode on the device

- [ ] Small embedding models running in the pilot's browser through WebAssembly / ONNX Runtime Web, so search works in cruise with no connection.
- [ ] Local search over operator manuals cached in advance on the pilot's EFB.
