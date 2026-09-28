# Shehryar Irfan

I build LLM systems for small businesses and run them in production on my own Linux server: an AI phone receptionist, WhatsApp assistants, a job-search pipeline, and a fleet of 54 Claude Code agents that maintains them.
Every product has an offline eval gate, and every number below links to a dated result file.

Based in Berlin · Available for AI engineering work · Second-year computer science student (B.Sc., 2025 to 2028)

[sherrybuilds.com](https://sherrybuilds.com) · [sherry.aiops@gmail.com](mailto:sherry.aiops@gmail.com) · [LinkedIn](https://www.linkedin.com/in/shehryar-irfan-bb5469349) · [Portfolio repo](https://github.com/sherrybuilds-studio/ai-systems-portfolio)

---

## What I've built

| System | State | Evidence |
| --- | --- | --- |
| **[AI phone receptionist](https://github.com/sherrybuilds-studio/ai-systems-portfolio/tree/main/projects/voice-receptionist)**: Vapi voice agent in German and English with a FastAPI tool webhook for availability and bookings. It says it is an AI and gives the recording notice at the start of every call | Deployed, demo on request | 12 of 12 golden calls pass the outcome check ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-voice-receptionist-eval.json)) |
| **[Agent fleet with a self-healer](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/architecture/fleet-overview.md)**: 54 Claude Code agents in six teams on a Postgres-leased queue. A healer classifies every failure and requeues, skips or escalates it; a lander merges test-only and docs-only agent work once CI is green | Running | 2.4% hard failures over the 1,000 runs from 9 July to 24 September ([snapshot](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-24-fleet-stats.json)) |
| **[Job pipeline](https://github.com/sherrybuilds-studio/job-pipeline)**: daily scoring with a Telegram digest, plus a sourcing pass over company career boards that checks each posting is still open, then writes a tailored one-page CV and a cover letter cleared by an independent reviewer | Running daily | 83 career boards and 2,981 postings in one sourcing pass ([evidence, 2026-09-26](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-26-job-pipeline.json)) |
| **[WhatsApp product assistant](https://github.com/sherrybuilds-studio/commerce-rag-agent)** for a furniture brand: keyword and vector retrieval, semantic cache | Pilot | Prompt cut 38%, from 1,118 to 695 tokens per message, when retrieval replaced the full catalogue ([changelog, 2026-04-27](https://github.com/sherrybuilds-studio/commerce-rag-agent/blob/main/CHANGELOG.md)) |
| **[Restaurant reservation assistant](https://github.com/sherrybuilds-studio/reservation-agent)**: bookings, waitlist, reminders, grounded menu answers | Built, not deployed | 10 of 10 retrieval questions ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-restaurant-bot-eval.json)) |
| **[Sales OS](https://github.com/sherrybuilds-studio/ai-systems-portfolio/tree/main/projects/sales-os)**: finds local businesses likely to miss calls and prepares consent-first outreach that a person approves | Built, run by hand | 10 of 10 scorer cases ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-sales-os-eval.json)) |

**Next up:** a quote agent, a speed-to-lead agent, missed-call text-back, review replies and more, each built from parts that already run. See [what I can build next](https://github.com/sherrybuilds-studio/ai-systems-portfolio#what-i-can-build-next).

## Public repositories

| Repo | What it is |
| --- | --- |
| [ai-systems-portfolio](https://github.com/sherrybuilds-studio/ai-systems-portfolio) | Architecture notes and dated eval results for every system above |
| [job-pipeline](https://github.com/sherrybuilds-studio/job-pipeline) | Career-board sourcing, liveness check, rule-based scoring, tailored CV and cover letter with an honesty reviewer |
| [reservation-agent](https://github.com/sherrybuilds-studio/reservation-agent) | Restaurant assistant: reservations, waitlist, reminders, menu retrieval with an eval |
| [commerce-rag-agent](https://github.com/sherrybuilds-studio/commerce-rag-agent) | WhatsApp product assistant: hybrid retrieval, semantic cache, prompt-injection filter |
| [sherrybuilds.com](https://github.com/sherrybuilds-studio/sherrybuilds.com) | My site in Next.js. The evidence section is generated from the eval files at build time; releases need my approval before the server pulls them |

## How I work

- **A test before a claim.** Every product has an offline eval gate. The voice, restaurant and portfolio-chat gates run in CI on every push.
- **Compliance lives in code.** The receptionist states that it is an AI (EU AI Act Art. 50) and gives the recording notice (§201 StGB). Sales OS refuses to draft outreach without consent (UWG §7).
- **Failures get a cause.** The self-healer puts every failed run into a failure class, and no-LLM probes check the stack every 5 minutes.
- **Humans approve what leaves the building.** Outreach, job applications and review replies are drafts until a person sends them.

**Stack:** Python, FastAPI, Claude API and Claude Code, OpenRouter, Vapi, ChromaDB, sentence-transformers, PostgreSQL and Supabase, Docker, PM2, GitHub Actions, Next.js and TypeScript.
**Languages:** English (fluent), Urdu (native), German (A2, learning).
