# Projects

Full list. The two most active are also featured on the [main profile](./README.md) — this is the fuller picture.

---

### LLM Eval Harness
*Active — public repo*

Built to catch a specific failure class: LLMs don't crash when they're wrong, they just return something wrong formatted identically to something right. This harness targets confident fabrication (ungrounded fields returned with no signal they're made up) and non-determinism (unstable outputs at temperature=0, on fields the model can actually reason about).

Built against DeepSeek's API across both Anthropic-compatible and OpenAI-compatible schema endpoints — deliberately, since schema-surface differences turned out to change reliability characteristics even for the same underlying model and prompt.

**Stack:** Python, DeepSeek API, custom eval scaffolding
**Link:** [github.com/blizwing/eval-harness](https://github.com/blizwing/eval-harness)

---

### Job Applier
*Live — UAT deployment*

End-to-end job application automation. A Chrome extension (Manifest V3) combines selector-based field-type detection with a neural network for semantic profile-data matching — figuring out that a field wants "years of experience" vs. "expected salary" and filling it from the right source, rather than relying on brittle selector rules alone.

Backend handles Gmail OAuth for application tracking and routes generation tasks across multiple AI providers.

**Stack:** Python, FastAPI, PostgreSQL, Chrome Extension (MV3), semantic search, AWS Lightsail, Docker
**Live:** [jobsapp.blueflameapps.com](https://jobsapp.blueflameapps.com)

---

### Chronicle AI
*Active — Android*

A multi-mode Android application unifying persona chat, turn-based narrative gameplay, and a real-time persona simulation engine under one architecture. The core design problem: LLMs have no persistent memory, so the app has to build one.

Three-tier memory system — active context, episodic SQLite store with semantic retrieval, and persistent "canon" world state — decides what a conversation actually needs to remember versus what gets promoted into long-term continuity. A background simulation engine (WorkManager-driven) models character presence and routines independent of whether the app is even open. Inference is backend-agnostic — local `llama.cpp` or remote endpoints — with streaming response handling and structured output parsing.

**Stack:** Kotlin, Jetpack Compose, Room, WorkManager, `llama.cpp`
**Link:** repo is private for now — screenshots on request
