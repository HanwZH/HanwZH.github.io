# hanwzh.github.io — personal website

Plain static HTML + CSS. No build step, no dependencies, no Jekyll.

Published at <https://hanwzh.github.io>.

## Files

| File | What it is |
|---|---|
| `index.html` | Home page: short introduction and research focus |
| `research.html` | Working papers and work in progress, with abstracts |
| `teaching.html` | Teaching-assistant positions |
| `cv.html` | Placeholder — says the CV is available on request; drop a link or PDF here when ready |
| `style.css` | All styling (light + dark mode, responsive) |
| `img/hanwen-zhang.jpg` | Portrait |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is, not run Jekyll |

## Preview locally

From the root of this clone:

```
python3 -m http.server 4173 --bind 127.0.0.1
```

Then open <http://localhost:4173>. That is the whole toolchain — edit an HTML
file, reload the browser.

Two things that have bitten before:

- **Run it from this directory.** Started elsewhere, `http.server` serves
  *that* directory instead, so `/index.html` 404s. Started from your home
  folder it serves your home folder.
- **Keep `--bind 127.0.0.1`.** Without it `http.server` listens on every
  network interface, so anyone on the same WiFi can browse whatever
  directory it is serving.

If you edited a file on github.com, run `git pull` before previewing —
otherwise you are looking at the older local copy.

## Updating

Edit the HTML directly and push:

```
git add -A && git commit -m "Update site" && git push
```

No PDFs are hosted here by design: the CV and paper drafts are shared on
request, so the site links to neither. If that changes, drop the file in and
link it — remember an unlinked file at a known URL is still publicly fetchable
once the repo is public.

## Taking the site offline

GitHub does not allow a user-Pages site to be switched off while the repo is
public. Making the repo private is the way to take it offline.

## Custom domain (optional)

Add a file named `CNAME` containing just the domain (e.g. `hanwenzhang.com`),
then point the domain's DNS at GitHub Pages:

- `A` records for `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- `CNAME` record for `www` → `hanwzh.github.io`

## History

This repo starts from a single clean commit. The earlier history, including the
old Jekyll site, lives in the private repo `HanwZH/website-archive`.
