# Anirudh Vyas

Founder and product leader who still ships. I set the direction, lead the team, and write the hard parts myself. 22 years building software, now running my own company.

## What I'm building

**[Cyan](https://the-cyan.com)** — agentic, collaborative AI that glues media production end to end: pre-production, post, and delivery/distribution.

Mid-to-large productions lose 30–40% of operator hours coordinating a dozen disconnected tools — roughly **$2M/year** for a 50-person shop. Cyan closes those gaps. Teams craft workflows together in plain English ("ingest the English master, run QC, transcribe, translate to Spanish and Portuguese, insert ad breaks, route for review, deliver on approval"), Cyan compiles and runs them across every tool with a human at every gate, and the value shows up on a dashboard.

The moat is the integration layer: any media tool — Avid, Media Composer, Pro Tools, DaVinci Resolve, Frame.io, broadcast systems — becomes an installable plug-in. Hand the codegen service a vendor's API, SDK, HAR capture, or docs and it generates a tested plug-in in **hours instead of the usual 5 weeks and $30–50K**. Those plug-ins get named in workflows and form a marketplace.

Currently piloting with **Planetcast Media Services** for **IBC 2026**.

## How I operate

- **Product** — defined Cyan end-to-end: the plain-English workflow compiler, the plug-in codegen engine and marketplace, the pricing and packaging model.
- **Go-to-market** — founder-led enterprise sales, design-partner relationships, and a US + India beachhead strategy in a $78B market.
- **Engineering** — built the technical foundation myself (below). I don't hand off the parts I'd struggle to lead.
- **Leadership** — co-founded and lead the team; own the roadmap, priorities, and the calls between shipping fast and building right.

## How it's built

- **Plug-in codegen service (Rust)** — HAR / OpenAPI / vendor docs → a working, tested Python MCP server. Deterministic extraction where it can be, an LLM repair loop until tests are green, a human approval gate, then the plug-in is Blake3-hashed and indexed into the registry.
- **Cyan Lens (cloud)** — the orchestrator. A planner compiles a plain-English workflow into a DAG, retrieves the right plug-ins from the registry, and runs each step where it makes sense — local, local + cloud, or fully cloud — at an efficient cadence, with success checks and backtracking.
- **Plug-in registry** — a Blake3-indexed catalog with the tool-retrieval layer that feeds the planner.
- **XaeroID** — identity for the local/offline path. When a team runs Cyan without the cloud, there's no SSO to lean on, so XaeroID handles auth directly (Ed25519, `did:peer`).
- **XaeroFlux** — the bootstrap peer for the mesh: discovery and the direct device-to-device path so jobs can stay on a team's own machines.

Stack: **Rust (Tokio, Axum), SQLite, Python**. Earlier career: Scala (Akka, Spark), Go, Python — data engineering and microservices at scale and in a different lifetime a lot of products that scale. 

## Track record

Principal Engineer at **Workday**; earlier at **Thomson Reuters** and **Wells Fargo**. Advisor to **Planetcast Media**. ~$2M+ in operational cost savings delivered across roles.

Previously **DrippLab** (fka Goldilocks Fashion) — LoRA-driven models for fashion classification and styling guidance. Now wound down; I plan to open-source some of those models.

## Contact

📧 anirudh.vyas@the-cyan.com · 🌐 [the-cyan.com](https://the-cyan.com)
