# Portfolio site: project spec

Single-page personal portfolio for **Prasad Potdar**, Senior Full Stack Developer. Static site, no build step, deployed on GitHub Pages.
Keep this file in the repo root. `CLAUDE.md` imports it, so Claude Code loads it automatically.

## Goal
Make a client or recruiter confident in Prasad within seconds: current role, years of experience, leadership, core stack, and that he is open to all types of work and learns quickly.

## Files
- `index.html`: the whole site (HTML, CSS in one `<style>`, JS in one `<script>` at the end).
- `vasundhara.webp`: photo for the Vasundhara project card.
- `vns-shop.webp`, `vns-planner.webp`, `vns-product.webp`: 1200×750 screenshots of public Vasundhara pages (shop, tank planner, a product page), captured 2026-10-18. Must never show the business city (the live site footer does, so crop to the top of the page).
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
- Remote in every role. Based in Maharashtra, India. Based in IST (UTC+5:30) and open to working with other time zones; both shown in profile.json and contact.
- Open to all types of work, and open for consultation.
- LinkedIn: https://www.linkedin.com/in/prasad-potdar-b43a5412a
- Public contact email: prasadmpotdar22@gmail.com (Prasad chose to publish it). Shown in the contact card and footer.
- Do NOT publish: date of birth, any other email address, exact city, family details.

**Experience**
CV figures are shown softened, as approximate team results ("helping", "about", "contributing to"), at Prasad's request. Source for dates, titles and figures below: Prasad's CV (`Prasad_Potdar_Resume_Revised.docx`, local only, git-ignored). Never publish its phone number, city or university.
- Political Data Intelligence, via VoterCircle India (Mar 2022 to present): NestJS microservices on a shared-libraries architecture; background and async processing on RabbitMQ and BullMQ; serverless infrastructure as code with Pulumi; Flutter apps with a custom architecture using Provider and BLoC; formal architecture reviews as part of technical leadership; Kubernetes and CI/CD pipelines. From the CV: API response times cut by up to 40% under peak load (GraphQL/REST, data access, caching); Docker/Kubernetes on Jenkins CI/CD cut deployment time roughly in half; worked directly with product on scoping and delivery.
- ISITCA (Jul 2019 to Jul 2021, title Full Stack Developer; from the CV: 30% cut in time-to-market, monolith to microservices, Jenkins/Docker CI/CD halving deploy time, Jest/Cypress coverage up ~25%, performance reviews; early-stage startup, remote): team lead. Do not show the team size ("10 engineers") on the page, at Prasad's request (2026-10-26); present it as technical leadership. Owned requirement gathering, planning, estimates and task distribution; architecture and the software development lifecycle through to delivery; code reviews; mentoring and interviewing. The product is confidential: do not describe it.
- Step Set Go (Jul 2021 to Mar 2022, Full Stack Developer, remote): payment services on Razorpay and Paytm with automatic gateway failover, 99.9% uptime; transaction success up ~25%; high-concurrency query and load-balancing work; React and Angular front ends.
- Freelance, Full Stack and Mobile Developer (Aug 2017 to Jul 2019, remote): client web and mobile apps in Node.js, PHP/Laravel, React, Flutter; requirement analysis with clients; mentored interns.
- No résumé PDF: LinkedIn is the full career history ("Full career history on LinkedIn" link under the timeline).

**Services (confirmed by Prasad, 2026-10-18; employer allows outside paid work)**
- Web app development, Mobile app development (added 2026-10-26), Architecture reviews, Backend and platform, AI features and automation, MVP build and delivery, Websites and CRMs, plus "anything else in software".

**Stack (all confirmed by Prasad; CV additions marked in the open items)**
- AI: Claude, OpenAI, Groq, Google Gemini, OpenRouter, RAG, Vercel AI SDK, spec-driven development. Learning: Agentic AI. ("Grok" was replaced by Groq, the provider actually used in Vasundhara.)
- Languages: TypeScript, JavaScript, Python, Java, SQL.
- Backend: Node.js, NestJS, Express.js, Django, Microservices, RabbitMQ, BullMQ, background jobs.
- Frontend and mobile: React, Next.js, Angular, Vue.js, Tailwind CSS, Bootstrap, HTML5/CSS3, Flutter, Provider, BLoC, React Native.
- Databases: PostgreSQL, MongoDB, MySQL, Redis, Neon, Drizzle ORM.
- APIs and security: REST, GraphQL, WebSockets, JWT, OAuth, Better Auth, zod.
- Cloud and delivery: AWS (Lambda, EC2, S3, SQS), Vercel (hosting), Cloudflare R2, Docker, Kubernetes, Pulumi, Git, GitHub Actions, Jenkins, deployment pipelines, CI/CD.
- Testing: Jest, Supertest, Mocha, Cypress, Playwright, Flutter test, Postman.
- Architecture and leadership: system design, distributed systems, API design, shared libraries, architecture reviews, code reviews, technical leadership, mentoring, hiring and interviewing.
- AI tools: GitHub Copilot (in the AI tile next to the model providers).
- Domains (CV summary): fintech, civic tech, startups. Education: B.E. Computer Science and Engineering, 2017 (university not named, it reveals the city).

**Project**
- Vasundhara Nature Studio, https://vasundharanaturestudio.com: production e-commerce and operations system for a real aquarium and aquascaping studio, built with AI. Facts below come from Prasad's own write-up (supplied 2026-10-17). The card shows only the highest-impact items, at Prasad's request: the three scale stats, a two-sentence intro, four highlights (inventory that can't be oversold, AI tank planner, grounded AI assistant, one pricing engine), the AI architecture line and the stack chips. Keep shop-specific operations detail (live-fish fees, WhatsApp claims, free-plan hosting) off the card.
  - Features: stock that cannot be oversold (reserved in a DB transaction, concurrent race tests, counter sales flow back, unpaid orders expire); Plan my tank (wizard, AI-written plan refined by chat, becomes a studio quote or ready-made cart); Vasu AI assistant grounded in the shop's species data, and "Help me choose" picks only in-stock products that fit the tank, fish and budget; one pricing engine for options, pack prices, offers, coupons and bundles, used by cart, delivery estimate and order; checkout for India (zone and weight estimates, flat per-box fee for live fish, staff-confirmed charge, UPI link or QR, live-arrival guarantee with WhatsApp claims, credit or refund); retention (saved tanks with "Will it suit my tank?", care-reminder emails, back-in-stock alerts, maintenance plans); fast and cheap to run (CDN pages refreshed on staff changes, Vercel free plan, Neon Postgres, scheduled jobs, cookie-free analytics).
  - AI: provider-agnostic LLM layer, Groq first, then Gemini, then OpenRouter. Recommendations come from the shop database (products and species), so it only suggests what is in stock. AI endpoints are server-side only, rate-limited and token-capped.
  - Stack: Next.js 16, React 19, TypeScript, PostgreSQL (Neon), Drizzle ORM, Better Auth (email + Google), Tailwind CSS 4, zod, Vercel, Cloudflare R2.
  - Scale: 70 database tables; 48 automated test files run against a separate test database; first commit to production of the whole system in about 1 week.
  - Card image: `vasundhara.webp`, the site's own home hero photo.
  - Do not name the business's city on the portfolio (it would reveal Prasad's city).

**Background code lines are decoration only.** The classic languages shown there (C, PHP, Perl, BASIC, etc.) are NOT claimed skills. Never add them to the stack list unless Prasad confirms.

## Page structure
1. Sticky pill nav (`~/prasad-potdar` with blinking cursor, links, "Hire me"). Services hides under 520 px, Work under 400 px.
2. Hero: `$ whoami`, name, "Senior Full Stack Developer at Political Data Intelligence", rotating "I build ..." line (starts broad: "full-stack products, end to end"), lead copy (outcome first: "I build production software that solves real business problems."), two buttons for the two visitor paths ("Discuss a project" for clients, "Hiring? See my experience" for recruiters), legend for the code background. Right side: `profile.json` at-a-glance panel.
3. Experience timeline. Current role bullets are grouped under three themes: Architecture and backend, Cloud and delivery, Leadership and mobile.
4. Stack bento grid, "AI engineering" as the featured tile: practice chips first, provider names in a smaller secondary row, Agentic AI under Learning.
5. Selected work: Vasundhara Nature Studio card, with a row of three screenshots linking to the live pages; then a smaller "Payment gateway failover" card (Step Set Go, CV facts only, no stack chips). No separate case-study page (Prasad declined, 2026-10-18).
6. Services: "How I can help", five cards: Web app development and Mobile app development (wide, first row), then Backend and cloud architecture, AI integrations and automation, End-to-end MVP delivery and an "Also" line (architecture reviews, websites, online stores, CRMs, anything in software). Then "How I work", four numbered steps confirmed by Prasad (2026-10-26): free intro call; written scope, estimate and timeline; build in milestones with regular demos; deploy, hand over code and docs, support after launch.
7. Contact: closing card with two path cards (Hiring, Consulting), "Email about a project" / "Email about a role" (mailto with subject), "Copy email" (clipboard, falls back to showing the address) and LinkedIn, then footer. "Open to all types of work" appears once here and once in profile.json, not in the hero.

## Design system
Dark first, light follows `prefers-color-scheme`. All colours are CSS variables on `:root`.

| Token | Dark | Light |
|---|---|---|
| `--bg` | `#090e1a` | `#f5f7fc` |
| `--surface` | `#0f1626` | `#ffffff` |
| `--surface2` | `#162038` | `#eaeff9` |
| `--fg` | `#f2f5fc` | `#0a1022` |
| `--body` | `#b4bdd2` | `#424b63` |
| `--muted` | `#8390a8` | `#5f6982` |
| `--line` | `#1f2a44` | `#dbe1ef` |
| `--accent` | `#8aa2ff` | `#3550f0` |
| `--accent2` | `#6fe0c9` | `#0a806f` |

Type: display `Bricolage Grotesque` (800 for headings), body `Geist`, labels and code `Geist Mono`. Section labels are written like comments (`// Experience`).

## Motion (keep it calm)
Only these animate: hero fade-in, rotating "I build" line, top scroll-progress line, nav active state, pointer spotlight on stack panels, hover lifts, blinking nav cursor, and the drifting code canvas behind the hero (classic code in `--accent2`, modern in `--accent`). All of it must switch off under `prefers-reduced-motion`. The canvas pauses when off-screen or the tab is hidden. Do not add more moving elements.

## Quality bar
- No horizontal scroll at 360 px width.
- Check light and dark themes.
- Body text contrast stays readable over the code background (canvas alpha stays low).
- No console errors.
- Every claim on the page traces back to "Content rules" above.

## Deploy (GitHub Pages)
1. Create a public repo named `<username>.github.io`.
2. Commit `index.html`, `vasundhara.webp`, `vns-*.webp`, `og.png`, `robots.txt`, `sitemap.xml`, `README.md`, `PROJECT_SPEC.md`, `CLAUDE.md` to `main`.
3. Settings, Pages, Deploy from a branch, `main` and `/ (root)`.
4. Live at `https://<username>.github.io/`.
Optional free custom address: `<name>.is-a.dev` via a pull request to `is-a-dev/register`; read that repo's README first.

## Open items
- [x] Vasundhara card image: the site's home hero photo (`vasundhara.webp`).
- [x] Political Data Intelligence results added from the CV (40% faster APIs, deploy time halved).
- [x] Name the testing tools used: Jest, Supertest, Flutter test.
- [x] E2E tools: both Cypress and Playwright.
- [x] "Vercel" means both: hosting (Cloud and delivery) and the Vercel AI SDK (AI tile).
- [x] Vasundhara AI details added from the repo.
- [x] Stack updated with what Vasundhara uses: Groq (replacing Grok), Gemini, OpenRouter, Next.js, Tailwind CSS, Drizzle ORM, Better Auth, zod.
- [x] Vasundhara hosting: Vercel.
- [ ] Add AI repos to the Selected work section once they exist.
- [x] Résumé: none; link to LinkedIn instead.
- [x] Vasundhara screenshots (shop, planner, product). Still possible: the open AI assistant chat, staff screens (from Prasad), an architecture diagram.
- [x] ISITCA responsibilities added; product stays confidential.
- [x] Step Set Go and Freelance cards added from the CV.
- [x] CV skills, outcomes, domains and education added (2026-10-18).
- [x] Vasundhara metrics: 48 test files; ~1 week covers the whole system.
- [x] Consulting offerings listed; employer allows outside work.
- [x] Public contact email added: prasadmpotdar22@gmail.com.