# Mayowa Dada

**AI Product Engineer** — I build and operate production AI products.

Based in the UK. Founder of [SOLAT Technologies](https://solat.io).

---

## About

I take AI products from an ambiguous problem to running software: architecture, backend implementation, deployment, and the operational work that follows launch.

Most of what I know came from operating what I built. Running a live product with paying users means caring about the parts that are invisible when things go well — rate limits, abuse controls, error tracking, and finding out that a metric you trusted for months was measuring the wrong thing.

I try to pick the architecture a problem actually needs rather than the one its category expects, and I'm as interested in what a system can't do as what it can.

---

## What I work on

- LLM application design and long-context pipelines
- Structured prompting and output design
- Backend AI services — Python, FastAPI, async processing
- Production concerns: rate limiting, abuse prevention, instrumentation, billing
- Evaluating AI output quality, and being honest about where that's still manual

---

## Selected work

### [TubeMate](https://www.tube-mate.com/) — AI YouTube learning assistant

Live product on the web and as a [Chrome extension](https://chromewebstore.google.com/detail/aimdebelonkoafhpeckdpkdlnnmfeglj). Extracts transcripts, generates structured summaries, and answers follow-up questions grounded in the video.

Python/FastAPI, PostgreSQL, Redis, Gemini 2.5 Flash Lite via LangChain. Stripe billing, Sentry, PostHog.

**224 registered users · 130 summaries across 94 videos · ~79 hours of content processed** *(August 2026)*

The decision I get asked about most is choosing **long-context prompting over retrieval**. RAG is the default answer for "ask questions about a document", but target transcripts run 15–90 minutes, which fits inside the model's context window. Retrieval solves the problem of content that *can't* fit. Adopting it anyway would have meant an embedding call per video, a vector index to keep consistent with Postgres, latency on every question, and a new failure mode where the wrong chunk gets retrieved and the model answers confidently from it — in exchange for nothing a user could perceive.

Also built the layered response to registration abuse: an email verification gate on product use, per-IP registration and login limits, and fingerprint throttling on the unauthenticated endpoint.

### Client systems — via SOLAT

- **A community platform** on Next.js and Payload CMS. Chose self-hosted over a hosted CMS because a nine-role permission model, audit logging and submission-queue ownership exceeded what hosted tooling offers without enterprise pricing plus a second admin app. Fourteen collections, WCAG 2.2 AA checks running in CI.
- **A booking and payments product** on Next.js, Supabase and Stripe. The interesting part is the availability engine: eight validity rules, all wall-clock times composed in Europe/London before overlap maths runs in UTC, and nineteen tests covering both BST and GMT. Get that wrong and bookings are an hour off for half the year.
- **Lahjiz Signaturez** — a made-to-order fashion storefront where the key decision was *not* building a cart, because the brand sells through conversation.

### ÒreAyò — speech recognition research

Early-stage research into automatic speech recognition for Nigerian languages: Yoruba, Igbo and Hausa. Pre-release.

---

## Tools

`Python` `TypeScript` `FastAPI` `PostgreSQL` `Redis` `LangChain` `Gemini`
`Next.js` `React` `Tailwind` `Payload CMS` `Supabase`
`Stripe` `Sentry` `PostHog` `Vitest` `Playwright` `Docker`

---

## Education

**MSc Management of Business Information Technology** — University of Greenwich, Distinction

**BSc Psychology**

---

## Contact

[LinkedIn](https://www.linkedin.com/in/mayowadada) · [mayowa.dada@solat.io](mailto:mayowa.dada@solat.io)

Open to AI engineering roles and collaboration.
