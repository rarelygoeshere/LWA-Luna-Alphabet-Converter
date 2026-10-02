# Luna Nova — Luna Alphabet Generator (archival mirror)

Offline-capable mirror of `https://ay.medyotan.ga/lunanova/` (live as of 29 Sep 2026),
a *Little Witch Academia* runic text converter. Pure client-side webfont substitution:
typed Latin text is rendered in the LWA rune fonts (`fonts/lwafont.otf`,
`fonts/lwafontcustom.otf`, by Nayas1 + /a/ anons — the fonts' internal name
tables credit "LWA Moonrunes", © 2017 Keith James, built with FontForge
(18 Jan 2017); the `custom` variant is subtitled "Punctuated"; PNG export via vendored
html2canvas 0.4.1 + FileSaver.js. No backend, no API calls, no build step.

Attribution links (FontStruct, 4chan thread, original site) are preserved in-page.

## Layout

- `index.html` — main generator (multi-file version)
- `old.htm` — legacy two-textarea version (uses `fonts/lwafont_1.otf`)
- `standalone.html` — single self-contained file (CSS, fonts, JS, images inlined as data URIs)
- `css/index.css` — styles; converter fonts embedded as Base64 (works over `file://`)
- `js/` — vendored html2canvas + FileSaver (no CDN dependency)
- `fonts/` — original `.otf` files for reference
- `assets/` — logo, chalkboard background, favicons, Luna Alphabet info chart

## Test locally

```powershell
cd lunanova-mirror
py -m http.server 8000
# open http://localhost:8000/
```

`standalone.html` also runs straight from disk (`file:///.../standalone.html`) —
open it directly, type text, toggle the three modes, and use PNGOUT.

## Deploy to GitHub Pages

1. Push this folder's contents to a repo root (or `gh-pages` branch).
2. Settings → Pages → Deploy from branch → `main` (or `gh-pages`), folder `/ (root)`.
3. No build step; all URLs are relative, so a project subpath
   (`user.github.io/repo/`) works unchanged.

## Verification checklist

- Type text → runes appear; newlines preserved; three radio modes switch fonts.
- PNGOUT downloads a `lunanova.png` render.
