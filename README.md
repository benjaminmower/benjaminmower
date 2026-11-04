# "Bronco" Benjamin Mower

I build AI agents and the infrastructure that decides what they're allowed to do. Days I run delivery on multi-million dollar Palisades Fire reconstruction projects in LA County. Nights and weekends I ship agent systems, evaluation harnesses, and the tooling around them.

Claude Code and Codex in terminal daily, because I see everyday problems and just plain want to make solutions. Everything below is code I wrote.

I come to this from entertainment and technology, where I've worked since 2008. I have designed production pipelines for Netflix, Amazon, and Warner Bros. Discovery productions, and I direct, produce, and write original work.

**[Resume](https://benjaminmower.github.io/portfolio/resume.html)** · **[Portfolio](https://benjaminmower.github.io/portfolio/)** · benjaminmower@gmail.com · Open to AI deployment, enablement, implementation and creative technology roles. Remote.

## Building now

**[Superintend](https://github.com/benjaminmower/superintend)** — An AI layer over project tracking that reads messy Google Sheets through a source-agnostic interface. Writes are restricted to AI-owned columns, every run supports a dry-run showing exact diffs, and contract tests gate any adapter before it touches a production project.

**Class management platform** *(private repo, in beta)* — A replacement for two commercial SaaS products, built after studying where one of them broke down for the business. Enrollment, scheduling, attendance, billing, curriculum progress, parent portal, admin operations, for a studio running hundreds of students across two locations with 20 employees. Working end to end including Stripe checkout against test data, not yet cut over. Postgres on Cloud SQL with no ORM: 16 tables, 12 enum types, 21 ordered raw-SQL migrations, views and triggers, migrations gated in Cloud Build so the app never reaches Cloud Run ahead of its schema. Two independent authorization layers — role-based plus a per-record ownership check, so a new endpoint fails closed rather than leaking by omission. The repo stays private because the system holds children's records.

**[Sendiment](https://benjaminmower.github.io/sendiment/)** — Anonymous ephemeral thoughts, shared between humans and AI assistants. A deployed remote MCP server on Cloudflare Workers with D1, published against the MCP schema with a versioned manifest and a streamable-HTTP endpoint, so any assistant can connect right now. No accounts, no names, no email. Rate limiting runs on a salted IP hash with the salt rotating daily and old hashes swept after two days, so the system can tell two posts share a source today without ever storing who that source is.

**[Tribute](https://github.com/benjaminmower/tribute)** — A browser extension that flags untested vibe-coded apps where you find them, backed by an agentic review harness. Apps earn a place on the register by passing a Tune Up: Playwright drives a real browser through the first-time customer journey and Claude grades five stages against a versioned rubric, with explainable reasoning on every score. TypeScript monorepo, Manifest V3, Zod-validated register shipped through CI to a `dist` branch and out over jsDelivr. Pre-alpha, five inaugural apps stress-testing the rubric.

**[lagsnap](https://github.com/benjaminmower/lagsnap)** — A Chrome extension that auto-converts screenshots for browser LLM conversations.

## Shipped

**[Flypost](https://github.com/benjaminmower/Flypost)** — A machine-readable registry of local events, built solo in three months against a six-month estimate for a team of engineers. Six AI agents built for three brokerages, deployed and trained with one of them before I wound the company down, each with a staff-facing agent that could publish and edit and a customer-facing agent that could only read, split on permissions. A published versioned MCP tool manifest and OpenAPI contract, verified end to end by connecting ChatGPT and Claude as clients and reading and seeding data through the API. Autonomous ingestion agent with three stop conditions and separate decision and proof logs, plus roughly 62 tests including anti-hallucination and server-authority suites. Infrastructure is switched off; the code is real.

**[HireNear](https://github.com/benjaminmower/hirenear)** — Map-first local job discovery. The agent extracts resume signals, discovers businesses, inspects sites, and scores fit; the human decides which doors to knock on. That confirmation step does three jobs at once: user control, natural rate limiting at human speed, and making each result feel earned. Prompt-injection framing on untrusted input, SSRF-safe URL validation, robots.txt parsed per origin, per-provider daily budgets, and a full non-LLM fallback path.

**[Beat the Fleet](https://github.com/benjaminmower/beat-the-fleet)** — Product concept and interactive mockup for gamifying autonomous vehicle rides.

## Entertainment work

**Production pipelines.** Entertainment and technology since 2008. I designed the data workflow from pre-production through production to post and VFX on productions and campaigns including Netflix Tudum, Tommy Hilfiger, DKNY featuring Hailey Bieber, Amazon Essentials, NARS, and Riot Games RiotNow, and kept chain of custody and audit-ready logging for footage that cannot be reshot. Tools: Silverstack Lab, Premiere Pro, Frame.io, DaVinci Resolve, Canva.

**Directing and producing.** Director and executive producer on [I Hope My Ex Doesn't See This](https://www.imdb.com/title/tt12328594/) and [Dark White](https://www.imdb.com/title/tt12280468/) (both 2020). Writer and creator credits on For Art's Sake and Prize or Punishment. [Full credits on IMDb](https://www.imdb.com/name/nm6156422/).

**Original formats.** Pitch decks for For Art's Sake, The Perfect Set, and Prize or Punishment, and game show demos for 100 for 100 (with Morgan Jay) and The College Try (with Brent Pella). Demos, decks, and credits are in the [portfolio](https://benjaminmower.github.io/portfolio/).

## Background

Eighteen years across construction, media production, and software. Currently Professional Services Program Manager at Elcano Construction, running two simultaneous multi-million dollar rebuilds. Before that, Technical Producer at Paramount+, where I replaced three asset-tracking systems with one, cut a six-hour daily process to 30 to 45 minutes, and wrote the playbooks the department standardized on — the system outlived the org chart that commissioned it. Since 2008, an entertainment technologist and creator on Netflix, Amazon, and Warner Bros. Discovery productions, designing production pipelines and directing and producing original work. Six years at Apple as a Technical Educator and Team Lead.

Reach me at benjaminmower@gmail.com.
