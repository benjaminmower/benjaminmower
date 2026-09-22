# Benjamin Mower

**I build the guardrails, interfaces, and evals that make AI agents safe to point at real systems — and the product decisions about when they shouldn't be.**

17 years running the operations systems behind physical work: construction program management and trade sequencing, creative marketing operations and production tracking at Paramount+, technical education and team leadership at Apple, production with Netflix, Amazon, and Warner Bros. Discovery. I've been the person whose schedule slips when a process fails — which is why I build agent tooling that earns trust before it gets authority.

**Day job:** Professional Services Program Manager on simultaneous multi-million dollar Palisades Fire reconstruction projects — trade sequencing, dependency tracking, and stakeholder communication across subcontractors, inspectors, and owners.

**After hours:** agent platforms, human-in-the-loop pipelines, and public MCP infrastructure — scoped, shipped, and measured against problems I've hit on a job site.

**Looking for:** product and program roles building agent platforms, AI implementation, and the evals and guardrails around them.

📍 Santa Monica, CA // Salt Lake City, UT · ✉️ benjaminmower@gmail.com · [LinkedIn](https://linkedin.com/in/benjaminmower) · [Résumé](resume.pdf)

---

## What I'm building

**[Superintend](https://github.com/benjaminmower/superintend)** — *Schedule risk detection on the tracker a construction team already uses.*

Construction schedules slip in the gap between "someone asked" and "someone answered." Superintend finds that gap in the weekly Google Sheet my Palisades Fire reconstruction projects run on — **280 items, 51 subcontractors, 39 weekly tabs** — and writes back a risk flag and one specific next action per item (*"Call Jimmy today to confirm gas pipe crew arrival; overdue since 8/31."*).

**The constraint that drove the design:** the superintendent is never going to adopt a new tool, and he's right not to — the tracker works. So the sheet stays the only interface the field and office teams touch. Adoption cost is zero, the rollout is reversible, and the agent writes only into columns it owns. Every construction-software company that asked a GC to migrate off their spreadsheet learned that lesson expensively.

**The scoping decision:** Sheets is the first adapter, not the architecture. Features run against a source-agnostic `TrackerSource` interface with capability flags, so a read-only CSV export or a Procore integration degrades gracefully instead of crashing — but I shipped exactly one adapter first, rather than building for customers who don't exist yet. One contract suite gates every adapter before it's trusted with a real project.

**The success criteria, defined before the results:** the risk rules are deterministic Python, so they can be **backtested against ~3,100 real recorded edits** — precision, recall, and lead time against three published baselines, with the slip definition frozen in advance so the numbers can't be tuned to flatter the tool. An agent layer that investigates each flagged item ships only if that eval says it beats the rules. If it doesn't, it ships off by default and the README says so.

Flagging is live on the real projects. Brief, weekly report, and the measured agent layer are next.

**[Sendiment](https://github.com/benjaminmower/sendiment)** — *An anonymous, ephemeral thought stream — and a public MCP server.*

Short anonymous "pebbles" fall down the screen; a stranger can skip one to keep it alive longer, otherwise it sinks and disappears for good. Runs as a remote MCP server on Cloudflare Workers with a D1 database, published to the MCP schema with a versioned server manifest and a streamable-HTTP endpoint, so any AI assistant can connect and cast a pebble too — agent casts render visibly distinct from human ones, because a reader should always know which they're looking at. Abuse is rate-limited through a salted, daily-rotating hash of the requester's IP, swept after two days, with no accounts, names, or raw addresses ever stored. Live at [benjaminmower.github.io/sendiment](https://benjaminmower.github.io/sendiment)

### Earlier work — paused in 2026, code remains public

**[Flypost](https://github.com/benjaminmower/Flypost)** — *A machine-readable local events registry with a production agentic ingestion loop.*

Claude Sonnet ran as the reasoning engine inside a tool loop that autonomously discovered sources, inspected pages via Playwright, extracted structured event data, deduplicated against Firestore, and published to the registry — with token budget guards and chain-of-custody proof logging per run. Shipped a versioned MCP tool manifest for the read surface, with tiered field access enforced structurally rather than by prompt, and separate agent-facing and client-facing surfaces because the publishing agent needed write permissions the client had no business holding.

**Why it's paused:** I killed the per-brokerage roadmap when Redfin and Compass shipped their own AI faster than I could build per-partner, pivoted to presence verification at open houses, and got it working with a real agent at Compass — then found that visitors wouldn't give feedback because it weakened their negotiating position. The technology worked; the incentive didn't. Mothballed on runway rather than rebuilt around a user need that wasn't there.

**[HireNear](https://github.com/benjaminmower/hirenear)** — *A map-first local hiring scout.*

Paste a resume, drop a pin, and HireNear walks the surrounding area identifying businesses with hiring signals. **Human-in-the-loop by design:** AI handles resume signal extraction, geospatial discovery, and fit scoring — the user drives every inspection decision, because the cost of a wrong automated outreach lands on the job seeker. Built with concurrent website inspection, real-time event emission via SSE, and a qualification-gated notification system. Public pages are statically prerendered for LLM discoverability with llms.txt, Schema.org JSON-LD, and AI citation baseline testing post-deploy.

**Also:** [Beat the Fleet](https://github.com/benjaminmower/beat-the-fleet) (gamified AV routing concept) · [lagsnap](https://github.com/benjaminmower/lagsnap) (Chrome extension for LLM-ready screenshots)

---

## How I think about AI risk

Every one of these ships with the same non-negotiables:

- **Allow-lists, not trust.** Agents never touch data or systems outside an explicit list — enforced in one function and covered by a test, not requested in a prompt.
- **Dry-run everything.** Every write path shows the exact diff before anything real happens.
- **Structural checks over prompted ones.** Contract tests, schema validation, tiered access, citation validation. A prompt asking nicely is not a control.
- **"Not found" is a valid answer.** When there isn't enough support, that's the output — never a guess.
- **Evals before authority.** Nothing points at a real system until it's been measured against what actually happened, with success criteria defined in advance and published even when they say the simpler approach won.

That last one is the part I care about most. It's easy to ship an agent that looks impressive. The work is proving it beats the boring deterministic baseline, on real data, and being willing to report when it didn't — then shipping the agent turned off.

## How I work

Claude Code and OpenAI Codex in the terminal daily — not as autocomplete, but as build partners. I write the spec, the guardrails, and the eval first; the agent writes most of the code against them.

I'm interested in where physical presence meets digital trust: where AI agents can produce verified, auditable ground truth that humans can actually act on. The hardest part is rarely the model — it's deciding what the agent is allowed to do, proving it does that, and designing the rollout so the people who have to live with it aren't asked to change first.
