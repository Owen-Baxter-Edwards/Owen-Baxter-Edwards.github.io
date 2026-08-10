# Owen Baxter Edwards — Portfolio

A single-page, dark-themed portfolio — the whole site (HTML, CSS, and JS) lives
in **one file**, `index.html`, plus one PDF. That's intentional: it means
there's no folder structure to get flattened, nested, or broken during upload,
which is what caused the site to render unstyled last time.

## What's inside — only 2 files

```
index.html                  Everything: markup + styling + behavior, self-contained
Owen_Edwards_Resume.pdf     Your résumé — viewable on-page and downloadable
```

Both files must sit at the **root** of your repo, side by side — not inside a
subfolder. That's the whole deployment.

## Why your last attempt showed an unstyled bulleted list

That happened because the CSS and JS were separate files inside `css/` and
`js/` folders, and GitHub's drag-and-drop uploader didn't preserve that
structure — so the browser couldn't find `css/style.css` and fell back to
completely unstyled HTML (which is exactly the plain, blue-link, bulleted-list
look you saw). This version has no separate CSS/JS files to lose, so that
specific failure mode is no longer possible.

## Publish it on GitHub Pages

You already have the repo (`Owen-Baxter-Edwards.github.io`). From here:

1. **Make the repository public.** GitHub Pages does not build from a private
   repository on the Free plan. Go to **Settings → General → Danger Zone →
   Change visibility → Make public**, and confirm. (The published *site* is
   always public either way — repo privacy only hides the source code.)
2. **Delete anything already in the repo** if your last upload left stray
   files/folders in there (e.g. an old `css/` or `js/` folder) — on the repo's
   file list, open each one and use the trash icon, or delete-and-re-upload is
   simplest.
3. **Upload the 2 files in this folder** — `index.html` and
   `Owen_Edwards_Resume.pdf` — via **Add file → Upload files**, dragging both
   in directly (not inside a folder). Commit to `main`.
4. **Settings → Pages** → Source: **Deploy from a branch**, branch **main**,
   folder **/(root)**. Save.
5. Wait 1–2 minutes, then visit `https://Owen-Baxter-Edwards.github.io/` —
   do a hard refresh (Ctrl/Cmd+Shift+R) since your browser may have cached the
   old broken version.

### Using git instead (more reliable than drag-and-drop)

```bash
cd path/to/this/folder
git init
git add index.html Owen_Edwards_Resume.pdf
git commit -m "Rebuild portfolio as a single self-contained page"
git branch -M main
git remote add origin https://github.com/Owen-Baxter-Edwards/Owen-Baxter-Edwards.github.io.git
git push -u origin main --force
```

(`--force` only needed if the repo already has a broken commit in it you want
to overwrite — drop it for a normal push to an empty repo.)

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
