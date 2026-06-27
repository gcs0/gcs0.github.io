# G. Çağatay Sat — Personal Website

A minimalist, academic-professional personal website built with **pure HTML, CSS, and vanilla JavaScript** — no frameworks, no build step. Designed to be deployed for free on **GitHub Pages**.

🔗 **Live (after deployment):** https://gcs0.github.io/

---

## ✨ Features

- Clean, single-page layout with smooth-scrolling navigation
- Sections: About · Education · Experience · Publications · Projects · Skills · Awards · Contact
- Fully responsive (mobile-friendly) with an accessible hamburger menu
- Subtle academic palette (black / white / gray + a tasteful burgundy accent)
- SEO-friendly meta tags + Open Graph tags
- Inline SVG favicon (no extra requests)
- Lightweight scroll-reveal animations (respects `prefers-reduced-motion`)
- Zero dependencies — loads instantly

---

## 📁 Project Structure

```
personal_website/
├── index.html              # Main page (all content lives here)
├── README.md               # This file
├── .nojekyll               # Tells GitHub Pages to serve files as-is
├── robots.txt              # SEO: allow crawlers + point to sitemap
├── sitemap.xml             # SEO: single-page sitemap
└── assets/
    ├── css/
    │   └── style.css       # All styles
    ├── js/
    │   └── main.js         # Mobile nav, scroll reveal, dynamic year
    └── img/
        └── favicon.svg     # Site favicon (initials "CS")
```

---

## 🚀 Deploy to GitHub Pages

Because the repository will be named **`gcs0.github.io`**, GitHub publishes it automatically as your main user site at `https://gcs0.github.io/`.

### Option A — Upload via the GitHub website (easiest, no Git needed)

1. Sign in to GitHub and click **New repository**.
2. Set the repository name to exactly **`gcs0.github.io`** (must match your username `gcs0`).
3. Choose **Public**, then click **Create repository**.
4. On the new repo page, click **uploading an existing file**.
5. Drag **all the files and folders** from this `personal_website/` directory (including the `assets/` folder, `index.html`, `.nojekyll`, etc.) into the upload area.
6. Click **Commit changes**.
7. Wait ~1 minute, then visit **https://gcs0.github.io/** 🎉

> Tip: make sure `index.html` ends up at the **root** of the repository, not inside a sub-folder.

### Option B — Using Git on the command line

```bash
# 1. Initialise the repo (run inside this folder)
git init
git add .
git commit -m "Initial commit: personal website"

# 2. Connect to GitHub (create the empty repo "gcs0.github.io" first)
git branch -M main
git remote add origin https://github.com/gcs0/gcs0.github.io.git

# 3. Push
git push -u origin main
```

Then go to your repo on GitHub → **Settings → Pages** and confirm:
- **Source:** Deploy from a branch
- **Branch:** `main` / `root`

Your site goes live at **https://gcs0.github.io/** within a minute or two.

---

## 🛠️ Editing the Content

All text content is in **`index.html`** — search for the section you want (e.g. `<!-- ===== Publications ===== -->`) and edit the text directly.

- **Colors / fonts:** edit the variables at the top of `assets/css/style.css` (`:root { ... }`).
- **Accent color:** change `--color-accent` (currently a deep burgundy `#8a1538`).
- **Favicon:** edit `assets/img/favicon.svg` (change the `CS` initials or color).

---

## 🧪 Preview Locally

No build tools required. Either:

- **Double-click `index.html`** to open it in your browser, **or**
- Serve it with a tiny local server (recommended for accurate paths):

```bash
# Python 3
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## 📄 License

Personal website content © G. Çağatay Sat. You are welcome to reuse the structure/code as a template.
