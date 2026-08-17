# Tushar Bhardwaj — Portfolio Site

A single-page portfolio built as a static site (plain HTML/CSS/JS — no build step, no
dependencies to install). It's designed to be hosted free on **GitHub Pages**.

```
site/
├── index.html
├── Tushar_Bhardwaj_Resume.pdf      ← linked from the "Download Resume" buttons
├── assets/
│   ├── css/style.css
│   ├── js/script.js
│   └── img/
│       ├── hero/                  ← hero background photo
│       ├── projects/              ← signature project photos & models
│       └── career/                ← early-career (L&T) photos
└── README.md
```

## ⚠️ Important — repo name must match the QR code

The resume PDF has a QR code baked in that points to:

**`https://tusharbhardwaj1406.github.io/`**

For that link (and QR code) to work, your GitHub repository must be named
**exactly** `tusharbhardwaj1406.github.io` (all lowercase). GitHub treats a repo
with that exact name as your personal root site — no extra `/repo-name/` in the
URL. If you use a different repo name instead, the site will still work fine, but
you'll need to tell me the name so I can regenerate the QR code with the correct
URL (`https://tusharbhardwaj1406.github.io/<that-name>/`).

## 1. Put this on GitHub

If you don't already have a GitHub account, create one free at github.com using
the username **tusharbhardwaj1406** (so the URL above resolves correctly).

**Option A — using the GitHub website (no command line needed)**
1. Go to github.com → **New repository**.
2. Name it **`tusharbhardwaj1406.github.io`** exactly (this is what makes the QR
   code on your resume work). Keep it **Public**. Don't add a README/gitignore
   (you already have one).
3. Click **Create repository**.
4. On the next page click **uploading an existing file**, then drag in *everything
   inside this `site/` folder* (index.html, the PDF, and the whole `assets` folder
   — GitHub's uploader supports dragging folders in most browsers).
5. Commit the files.

**Option B — using git from the command line**
```bash
cd site
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## 2. Turn on GitHub Pages
1. In your repository, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/(root)** → **Save**.
4. Wait ~1 minute, then refresh — GitHub shows the live URL at the top of that page
   (something like `https://tusharb.github.io/portfolio/`).

That's it — the site is live and free, and stays live as long as the repo exists.
Push any future changes to `main` and the site updates automatically in a minute or
two.

## 3. Custom domain (optional)
If you'd rather use your own domain (e.g. `tusharbhardwaj.com`):
1. Buy the domain from any registrar.
2. In **Settings → Pages → Custom domain**, enter it and save (this creates a `CNAME` file in the repo).
3. At your registrar, add a `CNAME` record pointing to `<your-username>.github.io`
   (for a subdomain) or the four GitHub Pages `A` records (for an apex domain) — GitHub's
   Pages settings page shows the exact records to add.

## 4. Updating content later
- **Resume**: replace `Tushar_Bhardwaj_Resume.pdf` with a new export (keep the same
  filename so the download buttons keep working), commit, push.
- **New project / photo**: drop the image in `assets/img/projects/`, then copy one of
  the `<article class="project">` blocks in `index.html` and edit the text, image
  paths, and span/dimension figures.
- **Contact details**: search `index.html` for the email/phone/LinkedIn — they each
  appear twice (hero-adjacent and footer).

## Notes
- No frameworks, no `npm install`, nothing to build — every file is served as-is,
  which is exactly what GitHub Pages expects.
- Images are already compressed for the web. If you add new ones, keep them under
  ~300KB each (JPEG, quality ~80) so the page stays fast on mobile.
- The site respects `prefers-reduced-motion` and is keyboard-navigable.
