# enp visuals — portfolio site

A single-page portfolio for **enp visuals** (video & photography), built as one static HTML file with local media and a JSON work list. No build step, no dependencies.

```
enp-visuals/
├── index.html              the whole site (styles, scripts, embedded Montserrat)
├── data/works.json         work list — the page reads this on load
└── media/                  sample stills (SVG) and clips (WebM)
```

## What's in it

- **Hero / About / Footer** — English copy with an EN · KO toggle (UI labels switch; work titles stay as written).
- **All · Video · Photo** — the sticky filter bar and the top nav both filter the page. `All` shows the Motion block and the Stills block.
- **Video cards** — poster + play affordance; the lightbox plays MP4/WebM directly, and YouTube / Vimeo links are embedded automatically.
- **Photo cards** — 4-up archive grid; the lightbox shows the image with year, role, client, camera and lens.
- **Lightbox** — ← → keys, swipe on phones, Esc to close.
- **Hidden admin** — double-click (or double-tap) the footer wordmark **or** the © line, enter `6160`.

## Editing works

Admin panel fields: type, title, year, role, description, video URL, poster URL, camera, lens, card shape, and a file upload. Uploads are stored as data URLs in this browser only.

- **Save** writes to `localStorage` (this browser, this device).
- **Export works.json** downloads the list including your edits.
- **Import** loads a `works.json` back in.
- **Reset samples** restores the shipped set.

### Publishing changes to the live site

1. Export `works.json` from the admin panel.
2. Replace `data/works.json` in the repository with it and commit.
3. For images/video, put the files in `media/` and use paths like `media/my-still.jpg` in the work's fields.

Visitors read `data/works.json`; they do not see your browser's local edits.

> The `6160` code is a quiet gate, not real security: the page is static, so anyone who reads the source can find it. It keeps the admin out of the way, nothing more. For a real lock, the edit action has to live on a server.

## Deploying (GitHub Pages)

The site is plain static files, so any static host works. For the address the brief asked for:

- **`https://enpvisuals.github.io`** — needs a GitHub account or organisation named `enpvisuals`, with a repository named `enpvisuals.github.io`. Upload the contents of this folder to the repository root and enable Pages (Settings → Pages → Deploy from branch → `main` / root).
- **Under the existing account (`@e0ruv`)** — create a repository named `enp-visuals`, upload the contents, enable Pages, and the site lives at `https://e0ruv.github.io/enp-visuals/`. All paths in the page are relative, so a subfolder works.

## Sample content

The seven sample works and their stills are placeholders, written to show the layout: three films (Nocturne, Grain & Light, Seoul 4AM) and four photographs (Static Bloom, Concrete Prayer, Blue Hour Apt. 402, Salt & Chrome). The clips are 4-second loops generated from the same artwork; the durations listed in the work data are fictional and should be replaced with the real running times.

`media/poster-*.svg` — graphic stills. `media/*.webm` — sample clips. Both can be deleted once real work is added.
