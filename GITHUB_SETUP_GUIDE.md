# GitHub Pages Setup Guide — aldennabil.github.io

Step-by-step instructions for publishing the portfolio website.

---

## Step 1 — Create the GitHub repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: **`aldennabil.github.io`** (must be exact — this activates GitHub Pages)
3. Visibility: **Public**
4. Do NOT initialize with README
5. Click **Create repository**

---

## Step 2 — Use al-folio as the template

1. Go to [github.com/alshedivat/al-folio](https://github.com/alshedivat/al-folio)
2. Click **"Use this template"** → **"Create a new repository"**
3. Name it `aldennabil.github.io`
4. Click **"Create repository from template"**

> This is better than forking — your repo stays independent.

---

## Step 3 — Enable GitHub Actions (auto-deploy)

1. In your new repo, go to **Settings → Pages**
2. Source: **"GitHub Actions"**
3. The site will auto-deploy on every push to `main`

---

## Step 4 — Copy the portfolio-site/ files into your repo

From the `Portfolio/portfolio-site/` folder in this workspace, copy:

```
_config.yml          → replace the default one
_pages/about.md      → replace default
_pages/projects.md   → replace default
_projects/           → copy all 10 .md files
assets/css/custom.css → add to the assets/css/ folder
_includes/head_custom.html → add (or merge with existing)
```

> Keep all other al-folio default files intact — they provide the theme's HTML structure and Jekyll plugins.

---

## Step 5 — Complete the config

Open `_config.yml` and fill in the three remaining fields:

```yaml
email: your.email@example.com
linkedin_username: your-linkedin-id    # the part after linkedin.com/in/
```

Also update the footer if needed:
```yaml
footer_text: >
  Alden Effendy · Statistics & Data Science · Institut Pertanian Bogor
```

---

## Step 6 — Add profile photo and CV

1. **Profile photo:** Rename your photo to `prof_pic.png` → place in `assets/img/`
2. **CV:** Export your CV as PDF → rename to `Alden_Effendy_CV.pdf` → place in `assets/pdf/`

---

## Step 7 — Add project cover images

For each project, create a cover image (PNG, ~1200×630px recommended):
- Extract the best figure from the project's notebooks/reports
- Crop tightly to the key chart
- Remove any background grid if it looks noisy
- Save as: `assets/img/projects/[project-slug].png`

| Project | File name |
|---------|-----------|
| Market Research Analytics Platform | `market-research-analytics-platform.png` |
| Football Outcome Prediction | `football-outcome-prediction-gammafest.png` |
| NOx Stacked Regression | `nox-prediction-stacked-regression.png` |

Tier 2 projects don't need cover images (they display as text cards only).

---

## Step 8 — Push and verify

```bash
git add .
git commit -m "feat: initial portfolio site"
git push origin main
```

Wait ~90 seconds, then visit: **https://aldennabil.github.io**

Check:
- [ ] Site loads correctly
- [ ] `/projects` shows all project cards
- [ ] Tier 1 project pages display with cover images
- [ ] LaTeX renders correctly (visit any project page with math)
- [ ] Mobile layout looks correct (test in Chrome DevTools)
- [ ] CV download link works

---

## Adding a New Project (future workflow)

1. **Create a GitHub repo** for the project (e.g., `aldennabil/new-project-slug`)
2. Copy `templates/project-skeleton/` → push to the new repo
3. Write `README.md` using `templates/PROJECT_README_TEMPLATE.md`
4. Copy `templates/WEBSITE_PROJECT_TEMPLATE.md` → `portfolio-site/_projects/new-project-slug.md`
5. Fill in the 8 YAML fields (title, description, img, importance, category, tags, github, year)
6. Add cover image to `portfolio-site/assets/img/projects/`
7. Push website changes → auto-deploys in ~90 seconds

Total time to add a new project: **under 30 minutes** (excluding the analysis itself).
