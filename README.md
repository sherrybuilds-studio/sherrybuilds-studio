# Shehryar Irfan

I build and run LLM systems on my own Linux server: a phone receptionist, a WhatsApp product assistant, a job-search pipeline, and the agent fleet that maintains them.
Each one has an offline test gate, and every number below links to a dated result file.
Second-year computer science student in Berlin (B.Sc., 2025 to 2028). Open to working-student roles, up to 20 h/week.

[sherrybuilds.com](https://sherrybuilds.com) · [sherry.aiops@gmail.com](mailto:sherry.aiops@gmail.com) · [LinkedIn](https://www.linkedin.com/in/shehryar-irfan-bb5469349) · [Portfolio repo](https://github.com/sherrybuilds-studio/ai-systems-portfolio)

---

## What I've built

| System | State | Evidence |
|---|---|---|
| **AI phone receptionist**: Vapi voice agent in German and English, FastAPI tool webhook for availability and bookings, AI disclosure and recording consent at the start of every call | Deployed. Demo on request | 12 of 12 golden calls pass the outcome check ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-voice-receptionist-eval.json)) |
| **Agent fleet with a self-healer**: Postgres-leased task queue, 36 enabled Claude Code agents (54 defined), a healer that classifies each failure and requeues, skips or escalates it | Running | 1,000 runs since 2026-07-09, 2.4% hard failures ([snapshot, 2026-09-24](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-24-fleet-stats.json)) |
| **Job pipeline**: daily scrape and rule-based scoring, plus a sourcing pass over company career boards, a tailored one-page CV, and a cover letter that a second model reviews | Running daily | 308 to 383 postings per daily run; 83 career boards, 2,981 postings in the 26 Sep sourcing pass ([evidence, 2026-09-26](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-26-job-pipeline.json)) |
| **WhatsApp product assistant** for a furniture brand: hybrid keyword and vector retrieval, semantic cache | Pilot | Prompt size cut 38%, 1,118 to 695 tokens per message, after replacing the full-catalogue prompt with retrieval ([changelog, 2026-04-27](https://github.com/sherrybuilds-studio/commerce-rag-agent/blob/main/CHANGELOG.md)) |
| **Restaurant reservation assistant**: bookings, waitlist, reminders, menu retrieval | Built, not deployed | 10 of 10 retrieval questions ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-restaurant-bot-eval.json)) |
| **Lead scoring for local businesses (Sales OS)** | Tested on one live run | 10 of 10 scorer cases ([eval, 2026-09-02](https://github.com/sherrybuilds-studio/ai-systems-portfolio/blob/main/evals/2026-09-02-sales-os-eval.json)) |

## Public repositories

| Repo | What it is |
|---|---|
| [ai-systems-portfolio](https://github.com/sherrybuilds-studio/ai-systems-portfolio) | Architecture notes and dated eval results for every system above |
| [sherrybuilds.com](https://github.com/sherrybuilds-studio/sherrybuilds.com) | My site in Next.js. The evidence section is generated from the eval JSON files at build time. Releases need my approval, and the server pulls them |
| [commerce-rag-agent](https://github.com/sherrybuilds-studio/commerce-rag-agent) | WhatsApp product assistant: hybrid retrieval, semantic cache, prompt-injection filter |
| [reservation-agent](https://github.com/sherrybuilds-studio/reservation-agent) | Restaurant assistant: reservations, waitlist, reminders, menu retrieval |

## How I work

- **A test before a claim.** Every product has an offline eval gate. The voice and restaurant gates run in CI on every push.
- **Compliance lives in code.** The receptionist states that it is an AI (EU AI Act Art. 50) and asks before recording (§201 StGB). Outreach drafts in Sales OS are blocked unless there is consent (UWG §7).
- **Failures get a cause.** The self-healer puts every failed run into a failure class. Six script probes with no LLM run every 5 minutes, and eight more look for silent failures.

**Stack:** Python, FastAPI, Claude API and Claude Code, OpenRouter, Vapi, ChromaDB, sentence-transformers, PostgreSQL and Supabase, Docker, PM2, GitHub Actions, Next.js and TypeScript.
**Languages:** English (fluent), Urdu (native), German (A2, learning).
