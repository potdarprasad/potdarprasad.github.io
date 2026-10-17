# Portfolio site: project spec

Single-page personal portfolio for **Prasad Potdar**, Senior Full Stack Developer. Static site, no build step, deployed on GitHub Pages.
Keep this file in the repo root. `CLAUDE.md` imports it, so Claude Code loads it automatically.

## Goal
Make a client or recruiter confident in Prasad within seconds: current role, years of experience, leadership, core stack, and that he is open to all types of work and learns quickly.

## Files
- `index.html`: the whole site (HTML, CSS in one `<style>`, JS in one `<script>` at the end).
- `vasundhara.webp`: photo for the Vasundhara project card.
- `og.png`: 1200×630 link-preview image (Open Graph) for LinkedIn, WhatsApp, etc.
- `README.md`: short deploy notes.
- `PROJECT_SPEC.md`: this file.
- `CLAUDE.md`: one line that imports this file for Claude Code.

No frameworks, no bundler, no npm dependencies. Fonts load from Google Fonts (Bricolage Grotesque, Geist, Geist Mono). Do not add dependencies unless there is a clear need.

## Content rules (source of truth)
Only use facts below. Do not invent employers, dates, metrics, skills, testimonials or project details. If something is missing, leave it out and add it to "Open items".

**Identity**
- Prasad Potdar, Senior Full Stack Developer at VoterCircle India Private Limited (Bangalore, remote), since Mar 2022.
- 9+ years of professional experience, career start Aug 2017.
- Remote in every role. Based in Maharashtra, India.
- Open to all types of work, and open for consultation.
- LinkedIn: https://www.linkedin.com/in/prasad-potdar-b43a5412a
- Public contact email: prasadmpotdar22@gmail.com (Prasad chose to publish it). Shown in the contact card and footer.
- Do NOT publish: date of birth, any other email address, exact city, family details.

**Experience**
- VoterCircle India (Mar 2022 to present): NestJS microservices on a shared-libraries architecture; background and async processing on RabbitMQ and BullMQ; serverless infrastructure as code with Pulumi; Flutter apps with a custom architecture using Provider and BLoC; formal architecture reviews as part of technical leadership; Kubernetes and CI/CD pipelines.
- ISITCA (2019 to 2021, early-stage startup, remote): led a team of 10 engineers.
- Also: Step Set Go, Freelance (no dates given).

**Stack (all confirmed by Prasad)**
- AI: Claude, OpenAI, Groq, Google Gemini, OpenRouter, RAG, Vercel AI SDK, spec-driven development. Learning: Agentic AI. ("Grok" was replaced by Groq, the provider actually used in Vasundhara.)
- Languages: TypeScript, JavaScript, Python.
- Backend: Node.js, NestJS, Microservices, RabbitMQ, BullMQ.
- Frontend and mobile: React, Next.js, Tailwind CSS, Angular, Flutter, Provider, BLoC.
- Databases: PostgreSQL, MongoDB, MySQL, Redis, Drizzle ORM.
- APIs and security: REST, GraphQL, WebSockets, JWT, OAuth, Better Auth, zod.
- Cloud and delivery: AWS (Lambda, EC2, S3, SQS), Vercel (hosting), Docker, Kubernetes, Pulumi, Git, GitHub Actions, deployment pipelines, CI/CD.
- Engineering practice: system design, architecture reviews, testing with Jest, Supertest, Cypress, Playwright, Flutter test.

**Project**
- Vasundhara Nature Studio, https://vasundharanaturestudio.com: a full online shop for an aquarium and aquascaping studio, built as an AI project. Source: Prasad's repo `vasundhara-nature-studio` (README and `docs/`). Prasad approved showing its features, AI and technologies.
  - Features: Plan my tank (wizard, AI-written plan, changes by chat, studio quote); "Vasu" AI assistant (care answers from the shop's species data, recommends only in-stock products); shop with live stock that cannot be oversold, delivery across India priced by zone and weight, UPI payments; My tanks (tank records, "Will it suit my tank?" check, email care reminders); staff admin (orders, stock, services, AI help for new species, cookie-free analytics).
  - AI: Groq (gpt-oss-120b), then Google Gemini, then OpenRouter as fallbacks; answers grounded in the shop's species and stock data; AI endpoints rate limited.
  - Built with: Next.js 16, React 19, TypeScript, PostgreSQL, Drizzle ORM, Better Auth (email and Google sign-in), Tailwind CSS 4, zod, sharp. Hosted on Vercel (confirmed from the live site's response headers; the repo README's "self-hosted" note is out of date).
  - Card image: `vasundhara.webp`, the site's own home hero photo.
  - Do not name the business's city on the portfolio (it would reveal Prasad's city).

**Background code lines are decoration only.** The classic languages shown there (C, PHP, Perl, BASIC, etc.) are NOT claimed skills. Never add them to the stack list unless Prasad confirms.

## Page structure
1. Sticky pill nav (`~/prasad-potdar` with blinking cursor, links, "Hire me").
2. Hero: `$ whoami`, name, "Senior Full Stack Developer at VoterCircle India", rotating "I build ..." line, lead copy, two buttons, legend for the code background. Right side: `profile.json` at-a-glance panel.
3. Experience timeline.
4. Stack bento grid, AI as the featured tile.
5. Selected work: Vasundhara Nature Studio card.
6. Contact: closing card with LinkedIn button, then footer.

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
2. Commit `index.html`, `vasundhara.webp`, `og.png`, `README.md`, `PROJECT_SPEC.md`, `CLAUDE.md` to `main`.
3. Settings, Pages, Deploy from a branch, `main` and `/ (root)`.
4. Live at `https://<username>.github.io/`.
Optional free custom address: `<name>.is-a.dev` via a pull request to `is-a-dev/register`; read that repo's README first.

## Open items
- [x] Vasundhara card image: the site's home hero photo (`vasundhara.webp`).
- [ ] One concrete result from the VoterCircle work (scale, speed, cost saved) for the experience card.
- [x] Name the testing tools used: Jest, Supertest, Flutter test.
- [x] E2E tools: both Cypress and Playwright.
- [x] "Vercel" means both: hosting (Cloud and delivery) and the Vercel AI SDK (AI tile).
- [x] Vasundhara AI details added from the repo.
- [x] Stack updated with what Vasundhara uses: Groq (replacing Grok), Gemini, OpenRouter, Next.js, Tailwind CSS, Drizzle ORM, Better Auth, zod.
- [x] Vasundhara hosting: Vercel.
- [ ] Commit `vasundhara.webp` along with the other files when deploying.
- [ ] Add AI repos to the Selected work section once they exist.
- [x] Public contact email added: prasadmpotdar22@gmail.com.