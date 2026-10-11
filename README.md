# Sieve — pitch deck

A reveal.js pitch for the Neurony Hackathon: one speaker, ~3 minutes, built
on the Sieve brand (dark slate, emerald, rose, mono) with original visuals and
rewritten copy — not the landing page's.

Deck arc: title → the problem → fearmongering (3 horror stories) → the promise
→ how it works → the error report → numbers → built different → live demo
handoff → roadmap → thank you / credits.

## Open it

No build step, no Node — the deck is static HTML plus vendored reveal.js:

```sh
open presentation/index.html        # macOS
# or serve it (needed only for PDF export / external markdown):
python3 -m http.server 8000          # then http://localhost:8000/presentation/
```

Opening `index.html` directly works because every slide is inline HTML — there
are no external Markdown or AJAX loads.

## Controls

- `→` / `←` — next / previous slide
- `F` — fullscreen
- `S` — speaker view (notes + next slide)
- `O` — slide overview
- `?` — all shortcuts

## Export to PDF

Serve the folder, then open with `?print-pdf` and print to PDF:

```sh
python3 -m http.server 8000
# open http://localhost:8000/presentation/?print-pdf and print
```

## Layout

```
index.html        the deck (11 slides, inline HTML + speaker notes)
theme/sieve.css   custom reveal.js theme — Sieve brand (slate, emerald, rose, mono)
dist/             reveal.js 6.0.2, vendored (reset.css, reveal.css, reveal.js)
favicon.svg       the mesh mark, copied from static/
```

reveal.js is vendored from the official basic setup (the `dist/` of the 6.0.2
release) rather than installed via npm, matching the project's "no Node, no
build step" rule — the same way `static/htmx.min.js` is vendored.
