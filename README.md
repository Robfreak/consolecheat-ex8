# Download-Zeit-Rechner

Wie lange dauert ein Download? Spielgröße durch Leitungsgeschwindigkeit, lokal gerechnet. Teil der inoffiziellen consolecheat-Werkzeuge rund um [consolecheat.com](https://consolecheat.com). German is the primary language, English is the other. Light and dark theme, self-hosted fonts, footer, Impressum, and Datenschutz are included. There is no Webmail link.

No account, no tracking, nothing uploaded. Fonts (Outfit, Source Sans 3) are self-hosted from `@fontsource`, so the page makes no request to Google or any other third party. The Impressum fields are placeholders until the operator fills them in. No name or address was invented.

Site: <https://robfreak.github.io/consolecheat-ex8/>

Inoffiziell. Nicht von Sony.

## What it does

A local estimate of how long a download takes: game size (GB or MB) divided by line speed (Mbit/s or MB/s). The page shows the bit/byte step (1 byte = 8 bits, 1 GB = 1 000 MB = 1 000 000 000 bytes, 1 MB/s = 8 Mbit/s). Nothing is uploaded. Size and speed are not stored, not even in `sessionStorage`. Defaults are 50 GB and 100 Mbit/s. Preset buttons are common game sizes (20, 50, 80, 100 GB) and common line speeds (50, 100, 250, 1000 Mbit/s). They are examples, not measurements from a store. 50 GB at 100 Mbit/s is 4 000 seconds (1 hour, 6 minutes, 40 seconds).

Open it at `/consolecheat-ex8/`. Language and appearance reuse `consolecheat-lang` and `consolecheat-theme`.

## Storage

- `consolecheat-lang` and `consolecheat-theme` (localStorage, shared with the other consolecheat tools on robfreak.github.io)

The Datenschutz page has a button that removes this page's keys. Nothing else is stored.

## Run and test

```bash
npm install
npm test        # node --experimental-strip-types --test src/download/*.test.ts
npm run dev     # http://127.0.0.1:5173/consolecheat-ex8/
npm run build   # typecheck, Vite build (base /consolecheat-ex8/), offline check of dist/
npm run preview # http://127.0.0.1:4173/consolecheat-ex8/
```

Node `>=22.6` (`package.json` `engines`).

## Files

- `index.html` — the HTML entry (Vite input)
- `src/download/` — React + TypeScript source, styles, and tests
- `src/download/tools.ts` + `src/download/tool-links.tsx` — the footer list **Weitere Werkzeuge** (keep it identical across the consolecheat repos)
- `public/` — `favicon.svg`, `FONT-OFL.txt`, `.nojekyll`
- `scripts/check-dist.mjs` — offline check of `dist/` (no third-party hosts, no `.woff` fallback, woff2 fonts present)
- `.github/workflows/pages.yml` — test, build, and deploy to `gh-pages`

## Other tools

The footer group **Weitere Werkzeuge** (English: **Other tools**) links to the other consolecheat tools: Title-ID-Finder (ex1), PS-Plus-Archiv (ex2), Controller-Tester (ex3), Save-Info-Leser (ex4), Fehlercode-Nachschlager (ex5), the [Spiele-Merkliste](https://robfreak.github.io/consolecheat-ex6/), and [Bildschirm-Test](https://robfreak.github.io/consolecheat-ex7/), [Tastenbelegung](https://robfreak.github.io/consolecheat-ex9/), [HDR/Helligkeit](https://robfreak.github.io/consolecheat-ex10/), [Audio-Kanal-Test](https://robfreak.github.io/consolecheat-ex11/), [USB-Stick-Checkliste](https://robfreak.github.io/consolecheat-ex12/), [Combo-Trainer](https://robfreak.github.io/consolecheat-ex13/), [Sprite-Animator](https://robfreak.github.io/consolecheat-ex14/). These are ordinary links. The page does not request those sites.

This tool was moved here from [Robfreak/consolecheat-ex6](https://github.com/Robfreak/consolecheat-ex6).

## GitHub Pages

`.github/workflows/pages.yml` runs install, test, and build on pull requests and on every push. A push to `main` also pushes `dist/` to the orphan branch `gh-pages` (`peaceiris/actions-gh-pages`, Jekyll off). Vite `base` is `/consolecheat-ex8/`, which matches the project site <https://robfreak.github.io/consolecheat-ex8/>.

Enable once in the repository settings:

1. **Settings → Actions → General → Workflow permissions → Read and write permissions.** Save.
2. **Settings → Pages → Build and deployment → Source: Deploy from a branch.** Branch: **`gh-pages`**, folder: **`/ (root)`.** Save.

After that, every push to `main` updates the site.

## Credits

Outfit and Source Sans 3 are bundled from `@fontsource` under the SIL Open Font License; see `public/FONT-OFL.txt` and `THIRD_PARTY_NOTICES.md`.

Replace the Impressum placeholders with the operator’s real details before treating that page as a legal notice.
