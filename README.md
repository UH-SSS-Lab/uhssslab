# UHSSS Lab website

A Jekyll site for the UHSSS Lab. Hosted free on GitHub Pages, served from
`uhssslab.com`.

This README covers the three things you'll do most: **edit content**,
**preview locally**, and **deploy**.

---

## TL;DR

- Edit a YAML or markdown file → commit → push → site updates automatically.
- Most edits don't need any code or local setup. You can do them in the
 GitHub web editor.

---

## 1. The 5-minute first-time setup

### a. Create a GitHub repo
1. Go to <https://github.com/new>
2. Name it whatever you like (e.g. `uhssslab-site`). Public is required for
 free GitHub Pages.
3. Don't add a README, .gitignore, or license, this folder already has them.

### b. Push this folder to it
From inside this folder, in a terminal:
```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<YOUR-USERNAME>/<REPO-NAME>.git
git push -u origin main
```

### c. Turn on GitHub Pages
1. In the repo on GitHub: **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. The workflow in `.github/workflows/pages.yml` will run and deploy the site
 automatically on every push to `main`.

### d. Point uhssslab.com at GitHub Pages
The `CNAME` file in this folder already contains `uhssslab.com`, so GitHub
will pick that up. You also need to update DNS at your domain registrar
(wherever you bought uhssslab.com, Wix, GoDaddy, Namecheap, etc.):

Add these **A records** for the apex (`uhssslab.com`):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
And a **CNAME record** for `www`:
```
www → <YOUR-USERNAME>.github.io
```
DNS can take up to a day to propagate. Once it does, GitHub will auto-issue
an HTTPS certificate (in Settings → Pages, check **Enforce HTTPS**).

> **Migrating from Wix?** Don't cancel Wix until DNS has switched and the new
> site is live, otherwise the domain may break briefly.

---

## 2. Editing content

You almost never need to touch HTML or CSS. The common edits:

| What you want to change | File to edit |
|---------------------------|----------------------------------|
| Lab name, tagline, PI bio | `_config.yml` |
| Add/remove people | `_data/people.yml` |
| Add a publication | `_data/publications.yml` |
| Add a news post | new file in `_posts/` (see below)|
| Add a research project | `_data/projects.yml` + `_projects/<slug>.md` |
| Edit Teaching page | `teaching.md` |
| Edit Contact page | `contact.md` |
| Change colors / fonts | top of `assets/css/main.scss` |

### Adding a person
Open `_data/people.yml` and copy an existing block:
```yaml
- name: Jane Doe
 category: PhD Students # PI / Postdocs / PhD Students / Masters Students / Undergraduates / Alumni
 role: PhD Student, Year 2
 photo: /assets/img/people/jane.jpg
 email: jane@example.edu
 scholar: https://scholar.google.com/...
```
Drop the photo into `/assets/img/people/`. Square images crop best.

### Adding a publication
Open `_data/publications.yml`, add an entry:
```yaml
- title: "The title of the paper"
 authors: "Doe, J., Smith, A., Your Name"
 venue: "NeurIPS 2026"
 year: 2026
 pdf: "https://link-to-pdf"
 doi: "https://doi.org/..."
 code: "https://github.com/..."
```
The Publications page automatically groups by year, newest first.

### Adding a news post
Create a new file in `_posts/` named `YYYY-MM-DD-short-slug.md`:
```markdown
---
title: "We won the Best Paper Award"
date: 2026-09-12
---

A short paragraph about the news. You can use **markdown**, [links](https://...),
and images.
```

### Adding a project page
1. In `_data/projects.yml`, add an entry with a `slug`.
2. In `_projects/`, create a file named `<slug>.md` with the long-form
 content. See `_projects/project-one.md` for a template.

---

## 3. Previewing locally (optional but recommended)

You don't *need* this, pushing to GitHub will show the result on the live
site. But if you want to see edits before they go live:

```bash
# one time:
gem install bundler
bundle install

# every time you want to preview:
bundle exec jekyll serve --livereload
```

Open <http://127.0.0.1:4000>. Edits hot-reload.

---

## 4. Deploying

Just commit and push:
```bash
git add .
git commit -m "Add new postdoc"
git push
```
The GitHub Action takes ~1–2 minutes, then the site updates at uhssslab.com.

You can also edit files directly on github.com (click any file → pencil
icon → Commit changes). That counts as a push and triggers a build.

---

## 5. Folder map

```
.
├── _config.yml ← site-wide settings (lab name, PI, social links, nav)
├── _data/ ← content as structured data
│ ├── people.yml
│ ├── publications.yml
│ └── projects.yml
├── _includes/ ← header, footer, head, edit if changing layout
├── _layouts/ ← page templates
├── _posts/ ← news posts (markdown, named YYYY-MM-DD-*.md)
├── _projects/ ← long-form project pages
├── assets/
│ ├── css/main.scss ← styling. Theme colors at the top.
│ ├── js/main.js
│ └── img/ ← photos, project images, favicon
├── index.html ← home page layout
├── people.html ← people page layout
├── publications.html ← publications page layout
├── news.html ← news index
├── research.html ← research index
├── teaching.md ← teaching page content
├── contact.md ← contact page content
├── CNAME ← uhssslab.com (custom domain)
├── Gemfile ← Ruby dependencies
└── .github/workflows/ ← GitHub Actions for auto-deploy
```

---

## 6. Common questions

**Can I change the colors?**
Yes, open `assets/css/main.scss` and change the `--c-accent` and related
variables at the top. The whole site re-themes.

**Can I add a new page?**
Yes. Create `mypage.md` with this header:
```markdown
---
layout: page
title: My Page
permalink: /mypage/
---
Content here.
```
Then add `{ title: "My Page", url: "/mypage/" }` to the `nav` list in
`_config.yml`.

**Something broke after I edited a file.**
Check the **Actions** tab on GitHub, the failed build will tell you what's
wrong (usually a YAML indentation error). Fix and push again.
