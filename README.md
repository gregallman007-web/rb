# Rathbone Advertising — static site (GitHub Pages ready)

19 pages, all self-contained. No build step, no dependencies to install.

## Contents

| File | Page |
|---|---|
| `index.html` | Homepage (scroll film hero) |
| `about.html` | About us |
| `contact.html` | Contact |
| `media-solutions.html` | Media Solutions hub (13 channels) |
| `our-work.html` | Our Work |
| `case-study-whitmore.html` | Sample case study |
| `radio.html` `outdoor.html` `press.html` `cinema.html` `tv.html` `direct-response.html` `ambient.html` | Traditional channels |
| `paid-search.html` `paid-social.html` `online-video.html` `display.html` `native.html` `audio.html` | Digital channels |
| `support.js` | Runtime the pages load (must stay alongside them) |
| `assets/` | Photography, composited ad mockups, client logos, six film clips |
| `logo/` | Rathbone monogram (gold, navy) |
| `.nojekyll` | Stops GitHub Pages ignoring underscore paths |

## Publish to GitHub Pages

From inside this `site/` folder:

```bash
git init
git add .
git commit -m "Rathbone Advertising site"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → Branch:
`main`, folder `/ (root)` → Save.**

Live within a minute or two at `https://<user>.github.io/<repo>/`.

To serve from a subfolder of an existing repo instead, copy this folder in as
e.g. `docs/` and pick **folder `/docs`** in the Pages settings.

## Check it locally first

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`. (Open the files directly via `file://` and
the film clips won't load — a local server is required.)

## Before going live

1. **Re-encode the film.** The six clips in `assets/` total ~16MB as delivered.
   See the `deploy/README.md` pack for HandBrake/ffmpeg settings — target 6–8MB
   with `-movflags +faststart`.
2. **Replace the placeholder statistics.** Every invented figure is marked with
   an asterisk (`*`). Swap in real RAJAR / Route / BARB numbers before launch.
3. **Fix the phone number and email** if they differ from
   `020 4571 9820` / `hello@rathboneadvertising.com` — both appear in the header,
   footer and CTAs of every page.
4. **Whitmore & Sons is a sample case study.** It's labelled as such on the page;
   remove or replace it with a real client once approved.
5. **Client logos** are used on the homepage and Our Work — confirm permission
   for each before publishing.

## Custom domain

Add a file named `CNAME` in this folder containing just the domain:

```
rathboneadvertising.com
```

Then point the domain's DNS at GitHub Pages (four A records for the apex, or a
CNAME record for `www`), and tick **Enforce HTTPS** in Settings → Pages.

## Notes

- Pages are static HTML; text edits are made directly in the files.
- The homepage film loads its clips into memory before scrubbing, so the hero
  needs a moment on a slow connection. Visitors with reduced-motion enabled skip
  the animation and land on the final brand frame with the call to action.
- Everything is responsive down to 390px.
