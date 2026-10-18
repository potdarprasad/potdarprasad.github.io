# Portfolio site: project spec

Single-page personal portfolio for **Prasad Potdar**, Senior Full Stack Developer. Static site, no build step, deployed on GitHub Pages.
Keep this file in the repo root. `CLAUDE.md` imports it, so Claude Code loads it automatically.

## Goal
Make a client or recruiter confident in Prasad within seconds: current role, years of experience, leadership, core stack, and that he is open to all types of work and learns quickly.

## Files
- `index.html`: the whole site (HTML, CSS in one `<style>`, JS in one `<script>` at the end).
- `vasundhara.webp`: photo for the Vasundhara project card.
- `og.png`: 1200×630 link-preview image (Open Graph) for LinkedIn, WhatsApp, etc.
- `robots.txt`, `sitemap.xml`: crawler hints for search engines.
- `README.md`: short deploy notes.
- `PROJECT_SPEC.md`: this file.
- `CLAUDE.md`: one line that imports this file for Claude Code.

No frameworks, no bundler, no npm dependencies. Fonts load from Google Fonts (Bricolage Grotesque, Geist, Geist Mono). Do not add dependencies unless there is a clear need.

## Content rules (source of truth)
Only use facts below. Do not invent employers, dates, metrics, skills, testimonials or project details. If something is missing, leave it out and add it to "Open items".

**Identity**
- Prasad Potdar, Senior Full Stack Developer at Political Data Intelligence (remote), since Mar 2022. Employed through VoterCircle India Private Limited (Bangalore), its Indian subsidiary. Lead with "Political Data Intelligence" everywhere; mention VoterCircle only as the subsidiary.
- 9+ years of professional experience, career start Aug 2017.
- Remote in every role. Based in Maharashtra, India.
- Open to all types of work, and open for consultation.
- LinkedIn: https://www.linkedin.com/in/prasad-potdar-b43a5412a
- Public contact email: prasadmpotdar22@gmail.com (Prasad chose to publish it). Shown in the contact card and footer.
- Do NOT publish: date of birth, any other email address, exact city, family details.

**Experience**
- Political Data Intelligence, via VoterCircle India (Mar 2022 to present): NestJS microservices on a shared-libraries architecture; background and async processing on RabbitMQ and BullMQ; serverless infrastructure as code with Pulumi; Flutter apps with a custom architecture using Provider and BLoC; formal architecture reviews as part of technical leadership; Kubernetes and CI/CD pipelines.
- ISITCA (2019 to 2021, early-stage startup, remote): led a team of 10 engineers.
- Also: Step Set Go, Freelance (no dates given).

**Stack (all confirmed by Prasad)**
- AI: Claude, OpenAI, Groq, Google Gemini, OpenRouter, RAG, Vercel AI SDK, spec-driven development. Learning: Agentic AI. ("Grok" was replaced by Groq, the provider actually used in Vasundhara.)
- Languages: TypeScript, JavaScript, Python.
- Backend: Node.js, NestJS, Microservices, RabbitMQ, BullMQ.
- Frontend and mobile: React, Next.js, Tailwind CSS, Angular, Flutter, Provider, BLoC.
- Databases: PostgreSQL, MongoDB, MySQL, Redis, Neon, Drizzle ORM.
- APIs and security: REST, GraphQL, WebSockets, JWT, OAuth, Better Auth, zod.
- Cloud and delivery: AWS (Lambda, EC2, S3, SQS), Vercel (hosting), Cloudflare R2, Docker, Kubernetes, Pulumi, Git, GitHub Actions, deployment pipelines, CI/CD.
- Engineering practice: system design, architecture reviews, testing with Jest, Supertest, Cypress, Playwright, Flutter test.

**Project**
- Vasundhara Nature Studio, https://vasundharanaturestudio.com: production e-commerce and operations system for a real aquarium and aquascaping studio, built with AI. Facts below come from Prasad's own write-up (supplied 2026-10-17). The card shows only the highest-impact items, at Prasad's request: the three scale stats, a two-sentence intro, four highlights (inventory that can't be oversold, AI tank planner, grounded AI assistant, one pricing engine), the AI architecture line and the stack chips. Keep shop-specific operations detail (live-fish fees, WhatsApp claims, free-plan hosting) off the card.
  - Features: stock that cannot be oversold (reserved in a DB transaction, concurrent race tests, counter sales flow back, unpaid orders expire); Plan my tank (wizard, AI-written plan refined by chat, becomes a studio quote or ready-made cart); Vasu AI assistant grounded in the shop's species data, and "Help me choose" picks only in-stock products that fit the tank, fish and budget; one pricing engine for options, pack prices, offers, coupons and bundles, used by cart, delivery estimate and order; checkout for India (zone and weight estimates, flat per-box fee for live fish, staff-confirmed charge, UPI link or QR, live-arrival guarantee with WhatsApp claims, credit or refund); retention (saved tanks with "Will it suit my tank?", care-reminder emails, back-in-stock alerts, maintenance plans); fast and cheap to run (CDN pages refreshed on staff changes, Vercel free plan, Neon Postgres, scheduled jobs, cookie-free analytics).
  - AI: provider-agnostic LLM layer, Groq first, then Gemini, then OpenRouter. Recommendations come from the shop database (products and species), so it only suggests what is in stock. AI endpoints are server-side only, rate-limited and token-capped.
  - Stack: Next.js 16, React 19, TypeScript, PostgreSQL (Neon), Drizzle ORM, Better Auth (email + Google), Tailwind CSS 4, zod, Vercel, Cloudflare R2.
  - Scale: 70 database tables; 48 automated test suites run against a separate test database; first commit to production in about 1 week.
  - Card image: `vasundhara.webp`, the site's own home hero photo.
  - Do not name the business's city on the portfolio (it would reveal Prasad's city).

**Background code lines are decoration only.** The classic languages shown there (C, PHP, Perl, BASIC, etc.) are NOT claimed skills. Never add them to the stack list unless Prasad confirms.

## Page structure
1. Sticky pill nav (`~/prasad-potdar` with blinking cursor, links, "Hire me").
2. Hero: `$ whoami`, name, "Senior Full Stack Developer at Political Data Intelligence", rotating "I build ..." line (starts broad: "full-stack products, end to end"), lead copy, two buttons for the two visitor paths ("Discuss a project" for clients, "Hiring? See my experience" for recruiters), legend for the code background. Right side: `profile.json` at-a-glance panel.
3. Experience timeline. Current role bullets are grouped under three themes: Architecture and backend, Cloud and delivery, Leadership and mobile.
4. Stack bento grid, "AI engineering" as the featured tile: practice chips first, provider names in a smaller secondary row, Agentic AI under Learning.
5. Selected work: Vasundhara Nature Studio card.
6. Contact: closing card with two path cards (Hiring, Consulting), "Email about a project" / "Email about a role" (mailto with subject) and LinkedIn, then footer. "Open to all types of work" appears once here and once in profile.json, not in the hero.

## Design system
Dark first, light follows `prefers-color-scheme`. All colours are CSS variables on `:root`.

| Token | Dark | Light |
|---|---|---|
| `--bg` | `#090e1a` | `#f5f7fc` |
| `--surface` | `#0f1626` | `#ffffff` |
| `--surface2` | `#162038` | `#eaeff9` |
| `--fg` | `#f2f5fc` | `#0a1022` |
| `--body` | `#b4bdd2` | `#424b63` |
| `--muted` | `#7a869f` | `#68728b` |
| `--line` | `#1f2a44` | `#dbe1ef` |
| `--accent` | `#8aa2ff` | `#3550f0` |
| `--accent2` | `#6fe0c9` | `#0e9c88` |

Type: display `Bricolage Grotesque` (800 for headings), body `Geist`, labels and code `Geist Mono`. Section labels are written like comments (`// Experience`).

## Motion (keep it calm)
Only these animate: hero fade-in, rotating "I build" line, top scroll-progress line, nav active state, scroll reveal on sections, pointer spotlight on stack panels, hover lifts, blinking nav cursor, and the drifting code canvas behind the hero (classic code in `--accent2`, modern in `--accent`). All of it must switch off under `prefers-reduced-motion`. The canvas pauses when off-screen or the tab is hidden. Do not add more moving elements.

## Quality bar
- No horizontal scroll at 360 px width.
- Check light and dark themes.
- Body text contrast stays readable over the code background (canvas alpha stays low).
- No console errors.
- Every claim on the page traces back to "Content rules" above.

## Deploy (GitHub Pages)
1. Create a public repo named `<username>.github.io`.
2. Commit `index.html`, `vasundhara.webp`, `og.png`, `robots.txt`, `sitemap.xml`, `README.md`, `PROJECT_SPEC.md`, `CLAUDE.md` to `main`.
3. Settings, Pages, Deploy from a branch, `main` and `/ (root)`.
4. Live at `https://<username>.github.io/`.
Optional free custom address: `<name>.is-a.dev` via a pull request to `is-a-dev/register`; read that repo's README first.

## Open items
- [x] Vasundhara card image: the site's home hero photo (`vasundhara.webp`).
- [ ] One concrete result from the Political Data Intelligence work (scale, speed, cost saved) for the experience card.
- [x] Name the testing tools used: Jest, Supertest, Flutter test.
- [x] E2E tools: both Cypress and Playwright.
- [x] "Vercel" means both: hosting (Cloud and delivery) and the Vercel AI SDK (AI tile).
- [x] Vasundhara AI details added from the repo.
- [x] Stack updated with what Vasundhara uses: Groq (replacing Grok), Gemini, OpenRouter, Next.js, Tailwind CSS, Drizzle ORM, Better Auth, zod.
- [x] Vasundhara hosting: Vercel.
- [ ] Add AI repos to the Selected work section once they exist.
- [ ] Résumé PDF for a download button (none in the repo yet).
- [ ] Real Vasundhara screenshots (storefront, tank planner, AI assistant, staff screens) and optionally an architecture diagram.
- [ ] ISITCA scope: what the team of 10 built and what Prasad owned (planning, reviews, mentoring, delivery).
- [ ] Step Set Go: dates, type of engagement, one contribution.
- [ ] Vasundhara metrics: confirm what "48 test suites" counts (files or suites), and what "~1 week to production" covers (first release vs whole system).
- [ ] Consulting: which offerings Prasad wants to list, and confirm the employer allows outside work.
- [x] Public contact email added: prasadmpotdar22@gmail.com.