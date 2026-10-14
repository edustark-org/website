# EduStark International — Website

A modern, fully static redesign of edustark.com. No build step, no framework, no
dependencies — just HTML, CSS and a few lines of vanilla JavaScript. Ready to host
on GitHub Pages (or any static host).

## Files

```
index.html                  Home page
tours-fall-2026.html        Fall 2026 undergraduate tours
tours-spring-2027-ug.html   Spring 2027 undergraduate tours
tours-spring-2027-grad.html Spring 2027 graduate tours
styles.css                  Shared design system / styles
main.js                     Mobile nav, scroll reveal, footer year
assets/favicon.svg          Site icon
.nojekyll                   Tells GitHub Pages to serve files as-is
```

## Preview locally

Just open `index.html` in a browser, or run a tiny local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a new GitHub repository (e.g. `edustark-site`).
2. Upload every file in this folder to the repo root (keep the `assets/` folder and
   `.nojekyll`). Via command line:
   ```bash
   git init
   git add .
   git commit -m "EduStark website"
   git branch -M main
   git remote add origin https://github.com/<your-username>/edustark-site.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment**.
   - Source: **Deploy from a branch**
   - Branch: **main** / **/(root)** → Save.
4. Wait ~1 minute. Your site goes live at
   `https://<your-username>.github.io/edustark-site/`.

### Using your own domain (edustark.com)

1. In **Settings → Pages → Custom domain**, enter `www.edustark.com` and save
   (this adds a `CNAME` file to the repo).
2. At your DNS provider, point `www` to `<your-username>.github.io` with a CNAME
   record. For the apex `edustark.com`, add the four GitHub Pages A records
   (see GitHub's "Managing a custom domain" docs) or a redirect.
3. Tick **Enforce HTTPS** once the certificate is issued.

> Note: edustark.com currently points to Wix. Switching the DNS/custom domain to
> GitHub Pages will replace the live Wix site — do this only when you're ready to
> go live.

## Before you go live — things to update

- **Contact email:** all "Book a Meeting" / contact links use
  `mailto:info@edustark.com`. Change this to your real address (search the files
  for `info@edustark.com`) or swap in a booking link (Calendly, Wix Bookings, etc.).
- **LinkedIn / socials:** the footer LinkedIn icon links to `#` — replace with your
  real profile URL.
- **Photos:** the design is image-light by intent so it loads fast and needs no
  stock photography. You can drop real photos into the hero, founder section and
  tour cards later — add images to `assets/` and reference them in the HTML/CSS.
- **Founder bio / stats:** copy is taken from the current site. Update the
  highlight numbers on the home page if you have firmer figures.

## Notes

- Fonts load from Google Fonts; everything else is self-contained.
- Works offline-friendly and on mobile (responsive down to small phones).
- Accessible: semantic landmarks, keyboard-operable nav, reduced-motion support.
