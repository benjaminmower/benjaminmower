## Hello World! I'm Benjamin Mower

I build systems at the intersection of physical operations and AI infrastructure. I design the guardrails, interfaces, and evals that make AI agents safe to run against real systems — not just the agents themselves.

Day job: Professional Services Program Manager on simultaneous multi-million dollar Palisades Fire reconstruction projects.

After hours: building autonomous agents, human-in-the-loop pipelines, and public MCP infrastructure that solve problems I've run into in the real world.

## What I'm building

**[Superintend](https://github.com/benjaminmower/superintend)** — The AI enablement layer I'm building for the real weekly tracker my own Palisades Fire reconstruction projects run on. The Google Sheet stays the only interface the field and office teams use — the agent reads its actual, messy structure (weekly tabs duplicated by hand, fill-down columns, multi-select statuses, a change log with no stable row keys) behind a source-agnostic `TrackerSource` interface, so Sheets is the first adapter, not the architecture. Writes are allow-listed to specific AI-owned columns and tabs, every write path supports `--dry-run`, and a contract test suite runs the same behavioral checks against every adapter before it's trusted with a real project. In progress.

**[Sendiment](https://github.com/benjaminmower/sendiment)** — An anonymous, ephemeral thought stream. Short anonymous "pebbles" fall down the screen; a stranger can skip one to keep it alive longer, otherwise it sinks and disappears for good. Runs as a remote MCP server on Cloudflare Workers with a D1 database, published to the MCP schema with a versioned server manifest and a streamable-HTTP endpoint, so any AI assistant can connect and cast a pebble too — agent casts render visibly distinct from human ones. Abuse is rate-limited through a salted, daily-rotating hash of the requester's IP, swept after two days, with no accounts, names, or raw addresses ever stored. Live at [benjaminmower.github.io/sendiment](https://benjaminmower.github.io/sendiment)

### Earlier work (paused in 2026, code remains public)

**[Flypost](https://github.com/benjaminmower/Flypost)** — A machine-readable local events registry with LLM-citeable endpoints and a production agentic ingestion loop. Claude Sonnet runs as the reasoning engine inside a tool loop that autonomously discovers sources, inspects pages via Playwright, extracts structured event data, deduplicates against Firestore, and publishes to the registry — with token budget guards and chain-of-custody proof logging per run. Also ships a versioned MCP tool manifest for the read surface, with full input and output schemas and tiered field access enforced structurally rather than by prompt.

**[HireNear](https://github.com/benjaminmower/hirenear)** — A map-first local hiring scout. Paste a resume, drop a pin, and HireNear walks the surrounding area identifying businesses with hiring signals. Human-in-the-loop by design: AI handles resume signal extraction, geospatial discovery, and fit scoring — the user drives inspection decisions. Built with concurrent website inspection, real-time event emission via SSE, and a qualification-gated notification system. Public pages are statically prerendered for LLM discoverability with llms.txt, Schema.org JSON-LD, and AI citation baseline testing post-deploy.

**Other:** [Beat the Fleet](https://github.com/benjaminmower/beat-the-fleet) (gamified AV routing concept) · [lagsnap](https://github.com/benjaminmower/lagsnap) (Chrome extension for LLM-ready screenshots)

## How I think about AI risk

Every one of these ships with the same non-negotiables: agents never touch data or systems outside an explicit allow-list, every write path has a dry-run mode that shows the exact diff before anything real happens, and outputs get checked structurally — contract tests, schema validation, tiered access — rather than trusted because a prompt asked nicely. When there isn't enough support for an answer, the answer is "not found," never a guess. Nothing gets pointed at a real system before it can be backtested against what actually happened.

## How I work

Claude Code and OpenAI Codex in terminal daily — not as autocomplete, but as collaborative build partners. I'm interested in the intersection of physical presence and digital trust: where AI agents can create verified, auditable ground truth that humans can actually act on.

## Background

17 years across construction, media production, and SaaS — running the operations systems behind the work: construction program management and trade sequencing at Elcano Construction, creative marketing operations and asset/production tracking at Paramount+, technical education and team leadership at Apple, plus production work with Netflix, Amazon, and Warner Bros. Discovery.

📍 Santa Monica, CA // Salt Lake City, UT
✉️ benjaminmower@gmail.com
