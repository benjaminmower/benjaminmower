## Hello World! I'm Benjamin Mower

I build systems at the intersection of physical operations and AI infrastructure.

Day job: Professional Services Program Manager on simultaneous multi-million dollar Palisades Fire reconstruction projects.
After hours: building autonomous agents, human-in-the-loop pipelines, and public MCP infrastructure that solve problems I've run into in the real world.

## What I'm building

**[Sendiment](https://github.com/benjaminmower/sendiment)** — An anonymous, ephemeral thought stream. Short anonymous "pebbles" fall down the screen; a stranger can skip one to keep it alive longer, otherwise it sinks and disappears for good. Runs as a remote MCP server on Cloudflare Workers with a D1 database, published to the MCP schema with a versioned server manifest and a streamable-HTTP endpoint, so any AI assistant can connect and cast a pebble too — agent casts render visibly distinct from human ones. Abuse is rate-limited through a salted, daily-rotating hash of the requester's IP, swept after two days, with no accounts, names, or raw addresses ever stored. Live at [benjaminmower.github.io/sendiment](https://benjaminmower.github.io/sendiment)

**[Flypost](https://github.com/benjaminmower/Flypost)** — A machine-readable
local events registry with LLM-citeable endpoints and a production agentic
ingestion loop. Claude Sonnet runs as the reasoning engine inside a tool loop
that autonomously discovers sources, inspects pages via Playwright, extracts
structured event data, deduplicates against Firestore, and publishes to the
registry — with token budget guards and chain-of-custody proof logging per run.
Also ships a versioned MCP tool manifest for the read surface, with full input
and output schemas and tiered field access enforced structurally rather than by
prompt. Paused in 2026 to focus on Sendiment; code and architecture remain public.

**[HireNear](https://github.com/benjaminmower/hirenear)** — A map-first local
hiring scout. Paste a resume, drop a pin, and HireNear walks the surrounding
area identifying businesses with hiring signals. Human-in-the-loop by design:
AI handles resume signal extraction, geospatial discovery, and fit scoring —
the user drives inspection decisions. Built with concurrent website inspection,
real-time event emission via SSE, and a qualification-gated notification system.
Public pages are statically prerendered for LLM discoverability with llms.txt,
Schema.org JSON-LD, and AI citation baseline testing post-deploy. Paused in 2026
alongside Flypost; code remains public.

**[Beat the Fleet](https://github.com/benjaminmower/beat-the-fleet)** — An
interactive product concept for gamifying autonomous vehicle routing. Riders
compete against the baseline AI to discover faster corridors, with fleet-wide
leaderboard mechanics. Live demo at benjaminmower.github.io/beat-the-fleet

**[lagsnap](https://github.com/benjaminmower/lagsnap)** — A Chrome extension
that auto-converts screenshots optimized for browser LLM conversations.

## How I work

Claude Code and OpenAI Codex in terminal daily — not as autocomplete, but as
collaborative build partners. I'm interested in the intersection of physical
presence and digital trust: where AI agents can create verified, auditable
ground truth that humans can actually act on.

## Background

17 years across construction, media production, and SaaS. Paramount Plus,
Elcano Construction, Apple, Netflix, Amazon, Warner Bros. Discovery.

📍 Santa Monica, CA // Salt Lake City, UT
✉️ benjaminmower@gmail.com
