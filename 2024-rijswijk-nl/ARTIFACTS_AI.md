# 2024 Rijswijk — AI / maintainer notes

**Audience:** AI agents and repo maintainers. The public **[README.md](README.md)** is intentionally minimal.

This tree mirrors the [agenda](../../content/2024-rijswijk-nl/agenda.md) and the Sessionize schedule (SessionNice alias **`MCTEU2024`**). Each leaf session folder is where slides and examples go. Session-level `README.md` files hold title, speaker list, and abstract from SessionNice.

## Naming

- **Per person:** `givenname-surname` (kebab-case). Expand German umlauts in folder slugs (**ü → `ue`**, same idea for ä/ö/ß).
- **Cohosted sessions / panels:** one folder; concatenate each `givenname-surname` in **alphabetical order by family name**.
- **Same speaker twice:** two session folders under the same `givenname-surname/`.
- **Solo folder only if needed:** create **`givenname-surname/`** when that speaker has **at least one** solo session. Cohost/panel-only speakers get no solo folder.

## Session slugs

Session folders use short kebab-case slugs (no dates), stable when you tweak titles slightly.

## Per-speaker README

In `{givenname-surname}/README.md` (and stacked blocks on cohost parents):

- **Title** `# {GivenName SurName}`, then **portrait** as an HTML **`<img>`** to the Sessionize CDN URL with **max 300px on the longest side**, then **bio** from SessionNice.
- **End of file:** `{GivenName SurName}: [Speaker profile](https://european-mct-summit-2024.sessionize.com/) on Sessionize` — link text is **Speaker profile**.

## Co-hosted and panel parent folders

- **Parent `README.md`:** one `# Speaker full name` block per person (H1), family-name order. Portrait + bio + footer each. Do not link to missing solo READMEs.

## Optional `_speakers/speakers.md` and profile screenshots

- **Path:** `_speakers/speakers.md` — generated from SessionNice (not `build_speakers_md.py`, which is run.events-only). This folder may be **gitignored**.
- **Regenerate:** re-run `Artifacts/_tools/Initialize-MctEu2024Artifacts.ps1` or a focused SessionNice export; keep parent/session stubs in sync with the schedule.

## Sessionize / SessionNice

| Item | Value |
| ---- | ----- |
| Artifacts / site slug | `2024-rijswijk-nl` |
| SessionNice alias | `MCTEU2024` |
| EventKey / site slug | `european-mct-summit-2024` |
| Public event | [https://european-mct-summit-2024.sessionize.com/](https://european-mct-summit-2024.sessionize.com/) |
| Venue | De Loods, Rijswijk, NL (14–17 January 2024) |

## Speakers without a public Sessionize directory page

Sessionize did not expose per-speaker public profile URIs for this event; footers point at the event site. Portraits use Sessionize CDN URLs when available.

_(listed for tracking)_
