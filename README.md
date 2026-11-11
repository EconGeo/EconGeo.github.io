# drewmueller.com — Quarto academic website

A research-forward personal academic site built with [Quarto](https://quarto.org).
Replaces the previous Adobe Portfolio site.

## Preview locally

```bash
quarto preview      # live-reloading local server at http://localhost:port
# or build once:
quarto render       # outputs to _site/
```

## Structure

| File | Page |
|------|------|
| `_quarto.yml` | Site config: navbar, theme, footer, social links |
| `index.qmd` | About / landing (headshot, bio, research interests, news) |
| `research.qmd` | Working papers with **embedded scrollable PDF previews** |
| `publications.qmd` | Publication list auto-generated from `publications.bib` |
| `teaching.qmd` | Courses, student projects, resources |
| `cv.qmd` | Embedded scrolling CV + download button |
| `contact.qmd` | Email and social links |
| `photo-credits.qmd` | Licenses and authors for the site photos (keep in sync with `assets/img/`) |
| `assets/img/` | Banner and card photos (Wikimedia Commons; see Photo credits) |
| `styles.scss` | Brand palette (ink blue + amber accent) and all page layouts: hero, cards, timelines |
| `assets/headshot.svg` | Placeholder headshot — replace with your photo |
| `cv/mueller-cv.pdf` | Placeholder CV — replace with your real CV |
| `papers/working-paper.pdf` | Placeholder paper — replace with real drafts |

## Things to replace before going live

- [ ] Headshot: swap `assets/headshot.svg` for a real photo (e.g. `headshot.jpg`),
      then update the `image:` field in `index.qmd`
- [ ] Google Scholar URL: replace `REPLACE_ME` in `_quarto.yml`, `index.qmd`,
      and `contact.qmd`
- [ ] Email: change `drewmueller@gmail.com` to your institutional address
- [ ] Bio text in `index.qmd`
- [ ] Real publications in `publications.bib` (paste BibTeX)
- [ ] Real working papers + PDFs in `research.qmd` / `papers/`
- [ ] Real CV at `cv/mueller-cv.pdf`

## Deploy to GitHub Pages

1. Create a GitHub repo named **`EconGeo.github.io`** (required for a user site).
2. Push this folder to it:
   ```bash
   git remote add origin git@github.com:EconGeo/EconGeo.github.io.git
   git branch -M main
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**
   (or set Source to the `gh-pages` branch — the included workflow publishes there).
4. The `.github/workflows/publish.yml` action renders the `.qmd` files and
   publishes on every push to `main`. No need to commit `_site/`.
5. Point your `drewmueller.com` domain at the site: add a `CNAME` file containing
   `drewmueller.com`, then set the custom domain in **Settings → Pages** and update
   your DNS (an `ALIAS`/`A` record per GitHub's custom-domain docs).

## Adding content later

- **A paper:** drop `your-paper.pdf` in `papers/`, copy a block in `research.qmd`.
- **A publication:** paste its BibTeX into `publications.bib`.
- **A course:** copy a course block in `teaching.qmd`.
