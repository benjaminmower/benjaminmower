# Benjamin Mower

I build AI agents and the infrastructure that decides what they're allowed to do. Days I run delivery on multi-million dollar Palisades Fire reconstruction projects in LA County. Nights and weekends I ship agent systems, evaluation harnesses, and the tooling around them.

Claude Code and Codex in terminal daily, as the method rather than autocomplete. Everything below is code I wrote.

## Building now

**[Tribute](https://github.com/benjaminmower/tribute)** — A browser extension that flags untested vibe-coded apps where you find them, backed by an agentic review harness. Apps earn a place on the register by passing a Tune Up: Playwright drives a real browser through the first-time customer journey and Claude grades five stages against a versioned rubric, with explainable reasoning on every score. TypeScript monorepo, Manifest V3, Zod-validated register shipped through CI to a `dist` branch and out over jsDelivr. Pre-alpha, five inaugural apps stress-testing the rubric.

**Superintend** — An AI layer over project tracking that reads messy Google Sheets through a source-agnostic interface. Writes are restricted to AI-owned columns, every run supports a dry-run showing exact diffs, and contract tests gate any adapter before it touches a production project.

**[Sendiment](https://sendiment.com)** — Anonymous ephemeral thoughts, shared between humans and AI assistants. A deployed remote MCP server on Cloudflare Workers with D1, published against the MCP schema with a versioned manifest and a streamable-HTTP endpoint, so any assistant can connect. No accounts, no names, no email. Rate limiting runs on a salted IP hash with the salt rotating daily and old hashes swept after two days, so the system can tell two posts share a source today without ever storing who that source is.

**[lagsnap](https://github.com/benjaminmower/lagsnap)** — A Chrome extension that auto-converts screenshots for browser LLM conversations.

## Shipped and in production

**Class management platform** *(private repo)* — Replaced two commercial SaaS products after studying where one of them broke down for the business. Enrollment, scheduling, attendance, billing, curriculum progress, parent portal, admin operations. A twenty-employee studio has run on it since 2024. Postgres on Cloud SQL with no ORM: 16 tables, 12 enum types, 21 ordered raw-SQL migrations, views and triggers, migrations gated in Cloud Build so the app never reaches Cloud Run ahead of its schema. Two independent authorization layers — role-based plus a per-record ownership check, so a new endpoint fails closed rather than leaking by omission. The repo stays private because the system holds children's records.

**[Flypost](https://github.com/benjaminmower/Flypost)** — A machine-readable registry of local events, built solo in three months against a six-month estimate for a team of engineers. Six production AI agents across three brokerages, each with a staff-facing agent that could publish and edit and a customer-facing agent that could only read, split on permissions. A published versioned MCP tool manifest and OpenAPI contract, verified end to end by connecting ChatGPT and Claude as clients and reading and seeding data through the API. Autonomous ingestion agent with three stop conditions and separate decision and proof logs, plus roughly 62 tests including anti-hallucination and server-authority suites. Infrastructure is switched off; the code is real.

**[HireNear](https://github.com/benjaminmower/hirenear)** — Map-first local job discovery. The agent extracts resume signals, discovers businesses, inspects sites, and scores fit; the human decides which doors to knock on. That confirmation step does three jobs at once: user control, natural rate limiting at human speed, and making each result feel earned. Prompt-injection framing on untrusted input, SSRF-safe URL validation, robots.txt parsed per origin, per-provider daily budgets, and a full non-LLM fallback path.

**[Beat the Fleet](https://github.com/benjaminmower/beat-the-fleet)** — Product concept and interactive mockup for gamifying autonomous vehicle rides.

## How I think about agent safety

Boundaries belong in code, not in documentation and hope.

- **Explicit allow-lists over trust.** Flypost's ingestion endpoint stripped every out-of-scope field before storage using both a forbidden-key list and a prefix rule, because documenting a separation fails the first time someone adds a field in a hurry.
- **Structural grounding over instruction.** Verified system data is stated as fact; model knowledge carries a mandatory disclosure marker. Telling a model not to hallucinate does not work. Giving it two tiers and a rule about which is which does.
- **Dry runs and exact diffs** before anything writes.
- **"Not found" over a plausible guess.** Anti-hallucination and server-authority tests check that the model never invents or overrides identifiers the server owns.
- **Bound every autonomous run.** Token budget, wall clock, and source count as independent stop conditions. Per-provider daily ceilings rather than one global cap, so a runaway dependency is obvious instead of hidden.
- **Log the why separately from the what.** A decision log and a proof log, because those are different investigations and one combined log serves neither.
- **Degrade, don't fail.** A non-LLM path throughout, so an unavailable or over-budget model still produces a real answer.

## Background

Seventeen years across construction, media production, and software. Currently Professional Services Program Manager at Elcano Construction, running two simultaneous multi-million dollar rebuilds. Before that, Technical Producer at Paramount+, where I replaced three asset-tracking systems with one, cut a six-hour daily process to under an hour, and wrote the playbooks the department standardized on — the system outlived the org chart that commissioned it. A decade as a Digital Image Technician and Solutions Architect on Netflix, Amazon, and Warner Bros. Discovery productions, and six years at Apple as a Technical Educator and Team Lead.

Reach me at benjaminmower@gmail.com.
