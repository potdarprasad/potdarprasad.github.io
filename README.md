# Prasad Potdar - portfolio

A single static page: `index.html`, plus two images (`vasundhara.webp` for the project card, `og.png` for link previews). Live at https://potdarprasad.github.io/. No build step, no dependencies (fonts load from Google Fonts).

## Deploy for free

### A. GitHub Pages (the chosen host, see `PROJECT_SPEC.md`)
1. Create a public repo named `<username>.github.io`.
2. Commit `index.html`, `vasundhara.webp`, `og.png`, `README.md`, `PROJECT_SPEC.md`, `CLAUDE.md` to `main`.
3. Settings -> Pages -> Deploy from a branch -> `main` / `(root)`.
4. Site appears at `https://<username>.github.io/`.

### B. Cloudflare Pages (alternative)
1. Create a free Cloudflare account (no card needed).
2. Workers & Pages -> Create -> Pages -> Upload assets (direct upload).
3. Drag in this folder (or the zip), deploy. You get `your-name.pages.dev`.

### C. Vercel
Works, but the Hobby plan is limited to non-commercial use. A portfolio you use to win paid work may count as commercial, so stick with A or B.

## Free custom domain (optional)
You do not need a domain. If you want a nicer address for free, request `yourname.is-a.dev`:
fork github.com/is-a-dev/register, add `domains/yourname.json` with a CNAME record pointing at your host
(e.g. `<username>.github.io`), open a pull request, and wait for approval. Read that repo's README first, as the rules can change.
Then add the same domain in your host's custom-domain settings.
A paid .com is optional and costs a small yearly registrar fee.

## Edit
Open `index.html`. Text content is plain HTML; colours are the variables at the top of the `<style>` block.
