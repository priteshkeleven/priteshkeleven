## Pritesh Kanani

Technical founder · applied ML and LLM systems engineer

Eight years shipping software, three building LLM systems in production. I run [Acasa Labs](https://acasalabs.com), am founding engineer at Notetube, and am a forward deployed engineer at Onda Works. Since December 2024 I've shipped nine AI and software products and client systems.

Most of that work comes down to one problem: getting useful work out of models I don't fully trust. I want to work on it full-time as empirical research, in scalable oversight, AI control, safeguards, and the ML systems and RL environments that make results trustworthy.

### How I build with models

- **Every extracted value quotes its source.** Code checks the quote is on the cited page. If it isn't, the value is dropped.
- **A second model checks the first.** When they disagree, a person decides.
- **Code, not the model, decides anything that pages a human.** The model interprets; data health and alert priority are computed.
- **A check that can't run is not a pass.** It's "unavailable", with a reason.
- **Evals are narrow, deterministic graders** that only check claims with a right answer. Taste-based grading drifts, so I leave it out.

### Selected work

**SigmaCPM** · extraction that has to prove each value · Django, Postgres, OCR, OpenRouter, 2026<br>
Reads construction tender PDFs and extracts line items and bond terms. Every value must quote its source page, so each output can be graded automatically, which also makes the task a natural RL environment. A second, adversarial pass re-checks bond terms; disagreements go to a disputed state for a person. Jobs run on a Postgres queue with leases, orphan reclaim, and skip-locked selection.

**Onda AI Analytics** · the model interprets, code decides · Python, FastAPI, OpenAI, 2026<br>
Collection, validation, and formulas run as deterministic Python before the model sees anything. Fails closed on unknown client or account mappings, uses read-only tools from an allowlist, and never fills in missing data. Methodology is versioned, each brief keeps its audit evidence, and rollout is gated: one client, then five, then the portfolio.

**FOOL the AI** · adversarial input to an LLM judge · FastAPI, Claude Haiku 4.5, React Native, in development<br>
A game where players try to get past a Claude judge with lateral answers. The judge scores predictability, validity, and creativity; fixed thresholds decide the verdict. A separate `INCOHERENT` outcome catches gibberish and exploit attempts, so gaming the judge counts as a loss. Every play is a labeled attempt to beat a judge, which could be used to study judge robustness and calibration.

**Agent-skill eval harness** · [linkedin-toolkit](https://github.com/priteshkeleven/linkedin-toolkit) · Python, 2026<br>
Runs an agent through about 7,000 lines of skill instructions against fixtures, then grades the output with deterministic graders (for example: did the rewrite keep the user's real numbers?). Test suites cover instruction integrity, security boundaries, and AI-text detection.

**Low-latency options trading platform** · confidential client · Python, Rust-core event engine, Redis, Parquet, DuckDB<br>
One event-driven code path for research, backtesting, paper trading, and live execution. Latency instrumented across 12 stages with exact percentile reservoirs. Measured in tape replay: 2.5 µs median / 8 µs p99 market-data decode, 21 µs median risk check, about 0.5 ms signal to order. The hot path never blocks: the dashboard publisher is bounded and drops data rather than slowing trading, and risk limits and a kill switch run before every order.

**Acasa Sentinel** · candidates, not verdicts · Gujarat Police Hackathon 2026 · YOLOv8, ByteTrack, DINOv2, pgvector<br>
Vendor-neutral CCTV pipeline: plate OCR with multi-frame voting and cross-camera vehicle re-identification on 768-d DINOv2 embeddings, all running locally. Watchlist hits go to an operator queue with evidence crops and an audit trail; route reconstruction rejects physically impossible hops and says why. On the hackathon sandbox: 24/24 plates matched, 0 false alarms in 100,000 unrelated plates, 5.7 ms per 1080p frame.

**Kraftr** · production image generation · Next.js, BullMQ, Redis, Postgres, GCP, 2026<br>
Turns one flat-lay photo into on-model fashion imagery up to 4K, keeping garment and model identity fixed across angles. Moderation on every generation; 7 job queues with worker heartbeats every 10 seconds.

### In progress

**RLCD** · calibrated decision models · self-directed, since September 2026<br>
Small single-pass models that return typed decisions with probabilities, trained so stated confidence matches observed accuracy. The method, evaluation plan (Brier, log score, ECE, temperature scaling), and a known-failure-modes list are written. Training hasn't started yet.

### Experience

| | |
|---|---|
| **Acasa Labs** · Founder & CTO | Mar 2025 – now |
| **Onda Works** · Forward Deployed Engineer | Sep 2026 – now |
| **Notetube** · Founding Engineer (grounded RAG over Qdrant, 5 model providers, web/iOS/Android/MCP) | Dec 2024 – now |
| **Ontario Power Generation** · Quantitative Methods Analyst | 2023 – 2024 |
| **Lamina Solutions** · ML Engineer intern (4/8-bit fine-tuning of Dolly-2.0 and LLaMA, response-bias evals) | 2023 |
| **Logilite Technologies** · Full-Stack Developer | 2018 – 2022 |

PG Diploma, Applied AI (George Brown College, Toronto) · B.E., Instrumentation and Control (GTU)

### Tools

**ML and LLMs:** PyTorch, Hugging Face Transformers, quantized fine-tuning, LLM-as-judge design, deterministic eval graders, RAG, Qdrant, pgvector, YOLOv8, DINOv2<br>
**Models and agents:** Anthropic, OpenAI, Gemini, and OpenRouter APIs, MCP servers, Claude Code skills and agents, human-in-the-loop review queues<br>
**Systems:** Python, TypeScript, Rust (event engine), SQL, FastAPI, Django, Next.js, Postgres, Redis, Prometheus, Grafana, Docker, GCP, AWS, Cloudflare Workers

### Open source

- [linkedin-toolkit](https://github.com/priteshkeleven/linkedin-toolkit), [x-toolkit](https://github.com/priteshkeleven/x-toolkit), [instagram-agent-skill](https://github.com/priteshkeleven/instagram-agent-skill): Claude skill bundles with tests and evals

### Elsewhere

I write *Building at the Edge* about how AI systems should show their work. Each post leads with a design decision and its reason.

[acasalabs.com](https://acasalabs.com) · [LinkedIn](https://linkedin.com/in/pritesh-k) · [X](https://x.com/priteshkeleven)

Surat, India · Canadian permanent resident, in Canada from January 2027 · open to San Francisco or remote
