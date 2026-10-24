# rgcosentino.github.io

Personal research website of Richard (Rick) G. Cosentino, built with [al-folio](https://github.com/alshedivat/al-folio) (Jekyll) and hosted free on GitHub Pages.

---

## One-time setup (about 15 minutes)

1. **Create the repository.** On GitHub, create a new **public** repository named exactly `rgcosentino.github.io`. Don't add a README or license.
2. **Upload these files.** Easiest: on your computer, unzip this folder, then in a terminal:
   ```bash
   cd rgcosentino.github.io
   git init -b main
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/rgcosentino/rgcosentino.github.io.git
   git push -u origin main
   ```
   (Make sure the hidden `.github/` folder is included; it holds the build workflow.)
3. **Allow the build to publish.** Repository → **Settings → Actions → General → Workflow permissions** → select **Read and write permissions** → Save.
4. **Wait for the first build.** Open the **Actions** tab. The "Deploy site" workflow runs automatically (about 5–10 minutes). When it shows a green check, a branch named `gh-pages` will exist.
5. **Turn on Pages.** **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `gh-pages` / `(root)`** → Save.
6. Visit **https://rgcosentino.github.io** after a minute or two.

From then on, every push to `main` rebuilds and republishes the site automatically. If a build fails, the Actions tab shows the error (usually a typo in a `.yml` or `.bib` file).

---

## Where everything lives

| To change… | Edit this |
| --- | --- |
| Bio on the home page | `_pages/about.md` |
| Your photo | replace `assets/img/prof_pic.jpg` (keep the same name) |
| Social/profile icons | `_data/socials.yml` (add your ORCID iD and Google Scholar ID) |
| Research themes page | `_pages/research.md` |
| Publications | `_bibliography/papers.bib` |
| Projects | one file per project in `_projects/` |
| News items on the home page | one file per item in `_news/` |
| Press / NASA videos | `_pages/press.md` |
| Talks, outreach, teaching | `_pages/talks.md` |
| Web CV | `_data/cv.yml`; PDF CV: replace `assets/pdf/Cosentino_CV.pdf` |
| Site name, description, settings | `_config.yml` |
| Menu order | `nav_order:` at the top of each page in `_pages/` |

You can edit any of these directly on github.com (open the file, click the pencil icon, commit), so you don't need a terminal for day-to-day updates.

---

## Common updates

### Add a publication
Easiest route: on [NASA ADS](https://ui.adsabs.harvard.edu), open the paper → **Export → BibTeX**, and paste the entry into `_bibliography/papers.bib`. Optional extras you can add inside the entry:

```bibtex
  selected = {true},          % also show on the home page
  abbr     = {PSJ},           % coloured journal badge
  preview  = {neptune.jpg},   % thumbnail from assets/img/publication_preview/
  pdf      = {mypaper.pdf},   % PDF button (put the file in assets/pdf/)
  bibtex_show = {true},       % "Bib" button
```

Tip: you can replace the whole file with an ADS export of your full library, then add `selected`/`preview` to your favourites. Several co-authored entries currently list "and others"; an ADS export will give the complete author lists and DOIs.

### Add a news item
Create `_news/2026-11-01-short-name.md`:

```markdown
---
layout: post
date: 2026-11-01
inline: true
related_posts: false
---

New ALMA Cycle 13 observations of Saturn's jets are in!
```

### Add a project
Copy any file in `_projects/`, rename it, and edit the top block:

```yaml
---
layout: page
title: My new project
description: One-line summary shown on the card
img: assets/img/my_image.jpg   # card image
importance: 3                  # order within its category (1 = first)
category: research             # research or mission
---
```

Then write the page in Markdown below it. To show images side by side, copy the `<div class="row">…</div>` block from an existing project.

### Add a press item or video
Copy one block in `_pages/press.md`. For a YouTube video, change the ID in `https://www.youtube.com/embed/VIDEO_ID`.

---

## Images

The planet and detector images in `assets/img/proj_*.jpg` are generated **placeholders**. Replace them with your own figures (ALMA wind maps, VLA images, HST maps, RFP diagrams), keeping the file names, or add new files and point to them. Landscape images around 1200×800 px work best for project cards.

---

## Previewing locally (optional)

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000. Docker users can run `docker compose up` instead (see `docs/INSTALL.md`).
