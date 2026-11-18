# Shehryar Irfan

I design, build and operate LLM systems for small businesses: an AI phone assistant, WhatsApp assistants, a job-search pipeline, and an autonomous agent fleet of Claude Code agents that maintains them.
Every number below carries its date and points to its source.

Based in Berlin · Founder of Frontkept since Oct 2026 · Available for AI engineering work · B.Sc. Computer Science, Arden University Berlin, Feb 2025 to Feb 2028, second year completed

[sherrybuilds.com](https://sherrybuilds.com) · [sherry.aiops@gmail.com](mailto:sherry.aiops@gmail.com) · [LinkedIn](https://www.linkedin.com/in/shehryar-irfan-bb5469349) · [Portfolio repo](https://github.com/sherrybuilds-studio/ai-systems-portfolio)

---

## What I've built

| System | State | Evidence |
| --- | --- | --- |
| **[Frontkept, an AI phone assistant](https://github.com/sherrybuilds-studio/ai-systems-portfolio/tree/main/projects/voice-receptionist)** for Berlin estate agents and property managers. Two voices share one FastAPI tool server of mine: Clara runs on ElevenLabs Agents and takes signed web calls, and Paul runs on OpenAI Realtime on a test line connected by SIP. It says in its first sentence that it is an AI, answers in German, with English in testing, and records no audio | Pilot, demo on request | Each new version passes a call simulator, the test suite and a separate review before I switch it on. Each call's AI-disclosure check is logged in a SHA-256 hash-chained journal (one chain per day), since 23 Aug 2026 |
| **[Agent fleet with a self-healer](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/architecture/fleet-overview.md)**: an autonomous agent fleet of headless Claude Code agents on a Postgres-leased queue. A healer classifies every failure and requeues, skips or escalates it; a lander merges test-only and docs-only agent work once CI is green. I work with parallel Claude Code lanes, each with a fixed role, a security lane that reads every change, and my approval before anything is released | Running | 6,598 runs (6,438 tasks) since 10 Jun 2026, as of 18 Nov 2026 ([count](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-11-18-fleet-runs.json)) |
| **[Job pipeline](https://github.com/sherrybuilds-studio/job-pipeline)**: scoring with a Telegram digest, plus a sourcing pass over company career boards that checks each posting is still open, then writes a tailored one-page CV and a cover letter cleared by an independent reviewer | Built, run on demand | 83 career boards and 2,981 postings in one sourcing pass ([evidence, 2026-09-26](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-26-job-pipeline.json)) |
| **[WhatsApp product assistant](https://github.com/sherrybuilds-studio/ai-systems-portfolio/tree/main/projects/commerce-rag-agent)** for a furniture brand: keyword and vector retrieval, semantic cache | Pilot, paused since 10 Oct 2026 | Prompt cut 38%, from 1,118 to 695 tokens per message, when retrieval replaced the full catalogue (measured 27 Apr 2026; the code is private) |
| **[Restaurant reservation assistant](https://github.com/sherrybuilds-studio/reservation-agent)**: bookings, waitlist, reminders, grounded menu answers | Built, not deployed | 10 of 10 retrieval questions ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-restaurant-bot-eval.json)) |
| **[Sales OS](https://github.com/sherrybuilds-studio/ai-systems-portfolio/tree/main/projects/sales-os)**: finds local businesses likely to miss calls and prepares consent-first outreach that a person approves | Built, run by hand | 10 of 10 scorer cases ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-sales-os-eval.json)) |

**Next up:** a quote agent, a speed-to-lead agent, missed-call text-back, review replies and more, each built from parts that already run. See [what I can build next](https://github.com/sherrybuilds-studio/ai-systems-portfolio#what-i-can-build-next).

## Public repositories

| Repo | What it is |
| --- | --- |
| [ai-systems-portfolio](https://github.com/sherrybuilds-studio/ai-systems-portfolio) | Architecture notes and dated eval results for the systems above |
| [job-pipeline](https://github.com/sherrybuilds-studio/job-pipeline) | Career-board sourcing, liveness check, rule-based scoring, tailored CV and cover letter with an honesty reviewer |
| [reservation-agent](https://github.com/sherrybuilds-studio/reservation-agent) | Restaurant assistant: reservations, waitlist, reminders, menu retrieval with an eval |

The phone assistant, the WhatsApp assistant and the code of [sherrybuilds.com](https://sherrybuilds.com) are private.

## How I work

- **A test before a claim.** Every product has an offline eval gate, and the voice, restaurant and portfolio-chat gates run in CI.
- **The rules are in the code.** The phone assistant says in its first sentence that it is an AI (EU AI Act Art. 50) and records no audio. Sales OS refuses to draft outreach without consent (UWG §7).
- **Failures get a cause.** The self-healer puts every failed run into a failure class, and no-LLM probes check the stack every 5 minutes.
- **Humans approve what leaves the building.** Outreach, job applications and review replies are drafts until a person sends them, and no change is released without my approval.

**Stack:** Python, FastAPI, Claude API and Claude Code, OpenRouter, ElevenLabs Agents, OpenAI Realtime, SIP, ChromaDB, sentence-transformers, PostgreSQL and Supabase, Docker, Caddy, Cloudflare Tunnel, Tailscale, GitHub Actions, Next.js and TypeScript.
**Coming next:** Grafana, Prometheus and Ansible.
**Languages:** English (fluent), Urdu (native), German (A2, learning).
