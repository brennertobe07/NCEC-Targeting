# CLAUDE.md — Vantage Election Explorer

Single-file HTML app showing NCEC targeting data for Virginia's 2026 cycle
(statewide / county / precinct Dem performance, with HD/SD/CD overlays and a
flagging-to-targets system). Live at **https://vantage.vadems.org**.

**Read `docs/REFERENCE.md` before any non-trivial change** — it has the full
feature map, data schema, metrics, styling, and regeneration steps.

## Quick facts
- **Repo:** `brennertobe07/Vantage` · **Main file:** `index.html` (data + CSS + JS all embedded; no build step)
- **Deploy:** commit + push to `main` → GitHub Pages serves it (root path; `CNAME` → vantage.vadems.org). ~1-2 min; hard-refresh to bust cache.
- **Data regen:** `python embed_ncec_data.py` re-embeds `NCEC_DATA` from the NCEC xlsx (path in the script).

## ⚠️ Not the same as `va-elections`
`brennertobe07/va-elections` is a *different* project — the **Virginia Candidate
Explorer** (candidate/donor data). Don't put Vantage changes there. See the note
at the top of `docs/REFERENCE.md`.

## Conventions
- Keep it single-file HTML — no build tooling, no new dependencies without asking.
- DPVA dark theme (shared CSS variables). Desktop-first, mobile-readable.
- When architecture/workflow changes, update `docs/REFERENCE.md` in the same task.
