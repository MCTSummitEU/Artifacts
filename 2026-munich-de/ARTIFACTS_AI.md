# 2026 Munich — AI / maintainer notes

**Audience:** AI agents and repo maintainers.

The public **[README.md](README.md)** **is the Friday agenda** (markdown table), not a one-line title. There is **no** separate `agenda.md`. Do not restore a one-line README. Saturday (Stadtführung) is not in this tree. Each leaf session folder is where slides and examples go.

## Event sources

This event is **Sessionize-only** (no run.events JSON).

| Item | Value |
| --- | --- |
| Sessionize slug | `mct-dach-community-meetup-2026` |
| HTML embed ID | `qrmdazch` |
| CFP / event | https://sessionize.com/mct-dach-community-meetup-2026/ |
| Public agenda | https://mctgermany.online/mct-community-meetup/ |
| Speakers embed | https://sessionize.com/api/v2/qrmdazch/view/Speakers |
| Sessions embed | https://sessionize.com/api/v2/qrmdazch/view/Sessions |

`https://sessionize.com/api/v2/qrmdazch/view/All` is **404** (HTML embed, not a JSON API). The site schedule API (`mct-dach-community-meetup-2026.sessionize.com/api/schedule`) is not published. Do not expect `Get-SnEventData -View All` to work until organizers add a JSON embed.

Public `sessionize.com/{speaker-slug}` profile pages were not found for this lineup. Speaker README footers use **on Sessionize** and link **Speaker profile** to the Speakers embed.

## Naming

- **Per person:** `givenname-surname` (kebab-case, e.g. `dieter-rauscher`, `michael-kirst-neshva`, `qin-li`). If a German umlaut appears in the display name or session slug, expand it (`ü` → **`ue`**, `ö` → **`oe`**, `ä` → **`ae`**). Display names on this event follow Sessionize (e.g. **Amelia Hernandez Osorio**, no accent).

- **Cohosted sessions (agenda lists multiple people):** one folder, **alphabetical order by family name**; for each person `givenname-surname`, concatenated. Example: `amelia-hernandez-osorio-andre-thiemann/vom-mct-zum-tsp-erfahrungswerte/`.

- **Solo folder only if needed:** create **`givenname-surname/`** when that speaker has **at least one** solo (non–co-hosted) session. Andre Thiemann is cohost-only on Friday — **no** `andre-thiemann/` folder.

- **Same speaker twice:** two session folders under the same `givenname-surname/` (see `daniel-kordes/`).

## Session slugs

Session folders use short kebab-case slugs (no dates), stable when you tweak titles slightly.

## Per-speaker README

In `{givenname-surname}/README.md`:

- **Title** `# {GivenName SurName}` (Sessionize spelling), then **portrait** as an HTML **`<img>`** to the Sessionize CDN (`https://cdn.sessionize.com/image/…`) with **max 300px on the longest side**, then **bio** from the Speakers embed.
- **End of file:** `{GivenName SurName}: [Speaker profile](https://sessionize.com/api/v2/qrmdazch/view/Speakers) on Sessionize` — link text is **Speaker profile**; the trailing **on Sessionize** is the platform name.

Session materials stay in `{givenname-surname}/{session-slug}/` as usual.

## Co-hosted parent folders

- **Parent `README.md` (`givenname-...-givenname/README.md`):** use **one `# Speaker full name` block per person** (H1, not `##`). For each: portrait as **HTML `<img>`**, full **inline** biography, then `{Name}: [Speaker profile](…) on Sessionize`. **Do not** link to `../givenname-surname/README.md` as a bio substitute. Stacked speaker sections only — see [`amelia-hernandez-osorio-andre-thiemann/README.md`](amelia-hernandez-osorio-andre-thiemann/README.md).

## Optional `_speakers/speakers.md` and profile screenshots

- **Path:** `_speakers/speakers.md` — not generated for this event (no JSON API). The folder is **gitignored**; see the Artifacts repo `.gitignore`.

## Speakers without a public Sessionize directory page

All Friday speakers: Amelia Hernandez Osorio, Andre Thiemann, Daniel Kordes, Dieter Rauscher, Michael Kirst-Neshva, Qin Li. Profiles are the Speakers embed only.
