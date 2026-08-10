# Owen Baxter Edwards — Portfolio

A single-page, dark-themed portfolio — the whole site (HTML, CSS, and JS) lives
in **one file**, `index.html`, plus one PDF. That's intentional: it means
there's no folder structure to get flattened, nested, or broken during upload.
## What's inside — only 2 files

```
index.html                  Everything: markup + styling + behavior, self-contained
Owen_Edwards_Resume.pdf     My résumé — viewable on-page and downloadable
```

Both files must sit at the **root** of the repo.

## Publish it on GitHub Pages

## Customizing later

Everything you'll want to change is marked `CUSTOMIZE ME` directly inside
`index.html` (search for that text):

- **Video introduction** — the `id="video-slot"` block in the Introduction
  section. Instructions for a YouTube/Vimeo embed or a self-hosted `.mp4` are
  written right above it as an HTML comment. If you add a video file, you can
  upload it straight to the repo root too (e.g. `intro.mp4`) — no folder
  needed, just update the `src` to match wherever you put it.
- **Project screenshots/charts** — each dashed placeholder block in the
  Selected Work section. Same approach: drop the image file at the repo root
  and point an `<img src="...">` at it.
- **Project links** — currently point to `#`; update once you have write-ups
  or repos to link to.
- **Industry Lens stats** — sourced from Salesforce's *2026 Data & Analytics
  Trends* report and 365 Data Science's *Data Analyst Job Outlook 2026*.
  Worth refreshing periodically so it reads as current, not a one-time
  snapshot.

If you're comfortable with folders and want to keep future assets organized
in a subfolder instead of the flat repo root, that's fine too — just make
sure you upload the *contents* of the folder (not the folder icon itself
dragged in a way that nests it one level deeper than intended), and double
check the live site after deploying.

## Local preview

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.
