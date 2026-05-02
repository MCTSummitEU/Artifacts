# 2026 Sarajevo — AI / maintainer notes

**Audience:** AI agents and repo maintainers. The public **[README.md](README.md)** is intentionally minimal.

This tree mirrors the [agenda](../../content/2026-sarajevo-ba/agenda.md). Each leaf session folder is where slides and examples go; nothing is in here yet.

## Naming

- **Per person:** `givenname-surname` (kebab-case, e.g. `jane-doe`, `nicky-de-westelinck`, `michael-kirst-neshva`). If a German umlaut appears in the display name, expand it in the folder slug (e.g. **Andreas Schlüter** in another year would be `andreas-schlueter`, ü → **`ue`**). If that person has **no** session linked 1:1 to run.events yet, prefix the speaker folder with **`_`** (e.g. `_eltjo-van-gulik`).

- **Cohosted sessions (agenda lists multiple people):** one folder, **alphabetical order by family name**; for each person `givenname-surname`, concatenated. Example: `damir-dizdarevic`, `robert-hales`, `jasmin-kahriman`, `rolf-mclaughlin` (D → H → K → Mc) →
  `_damir-dizdarevic-jasmin-kahriman-robert-hales-rolf-mclaughlin/_opening-session-and-keynote/` (leading `_` on the speaker folder when none of their sessions are matched 1:1 to run.events, and `_` on each unmatched session slug).
  and `amelia-hernandez-osorio-andre-thiemann/.../`.

- **Panels (like cohosted, same idea):** if the [public agenda](https://e.runevents.net/mct-eu-summit-2026) only lists a moderator, use **`{givenname-surname}-and-copanelists/{session-slug}/`**. Add full panelist names in that folder’s `README.md` (and in the [agenda](../../content/2026-sarajevo-ba/agenda.md) when confirmed). You can **rename** the cohost folder to the full `givenname-surname-...-givenname-surname` chain when you have a complete list.

- **Same speaker twice:** two session folders under the same `givenname-surname/`.

## Session slugs

Session folders use short kebab-case slugs (no dates), stable when you tweak titles slightly.

- **Not matched to run.events (1:1):** prefix the session folder name with **`_`** (e.g. `_johan-smarius/_storytelling-for-trainers`: underscore on the speaker parent when they are still “absent” from the API mapping, and on the session leaf).

## Per-speaker README

In `{givenname-surname}/README.md`:

- **Title** `# {GivenName SurName}` (or the name you use on mctsummit), then **portrait** as an HTML **`<img>`** to `https://cdn.runevents.net/speaker-profile-images/{uuid}` with **max 300px on the longest side** (see the `artifacts_speaker_portrait` helper in the mctsummiteu **mct-summit-eu-artifacts-speakers** skill), then **bio** (from API or event UI).
- **End of file:** `{GivenName SurName}: [Speaker profile](https://speakers.run.events/… ) on run.events` — link text is **Speaker profile**; the trailing **on run.events** is the platform name. For **Sessionize**-only events, use the same pattern with **on Sessionize** and the Sessionize profile URL. If there is no public directory, link **Speaker profile** to the in-app listing (e.g. event speakers); see **Engin Soysal**.

Session materials stay in `{givenname-surname}/{session-slug}/` as before.

## Co-hosted and panel parent folders

- **Solo folder only if needed:** create **`givenname-surname/`** when that speaker has **at least one** solo (non–co-hosted) session artifact tree. If they appear **only** in co-hosted or panel sessions, **do not** create a solo folder — their bio and profile live only in the combined parent `README.md` (see below).

- **Parent `README.md` (`givenname-...-givenname/README.md`):** use **one `# Speaker full name` block per person** (H1, not `##`). For each: portrait as **HTML `<img>`** to the CDN with **max 300px on the longest side** (see the `artifacts_speaker_portrait` helper in the skill), full **inline** biography (from API or copied from the site), then `{Name}: [Speaker profile](…) on run.events`. **Do not** link to `../givenname-surname/README.md` for speakers who have no solo folder. Do not use a single top-level “Panel:” title unless you want a one-line context; the reference is stacked speaker sections only — see [`amelia-hernandez-osorio-andre-thiemann/README.md`](amelia-hernandez-osorio-andre-thiemann/README.md).

- Session slide folders stay under the parent, e.g. `…/from-mct-to-tsp-sharing-learnings-from-the-road/`.

Examples:

- `amelia-hernandez-osorio-andre-thiemann/README.md` (cohost-only speakers)
- `ronald-beekelaar-sara-fennah-amelia-hernandez-osorio-rolf-mclaughlin/README.md` (panel; inline bios for all, including panelists who also have solo folders elsewhere)
- `thorsten-butz-rolf-masuch/README.md` (panel; Thorsten also has `thorsten-butz/` for other sessions — optional duplicate bio in the panel README per the stacked format)

## Optional `_speakers/speakers.md` and profile screenshots

- **Path:** `_speakers/speakers.md` — API-generated speaker list; optional **`_speakers/*.png`** profile screenshots (match by name; filenames may be timestamped). **Regenerate:** `build_speakers_md.py` with `MCT_RUNEVENTS_EVENT=mct-eu-summit-2026` and `MCT_ARTIFACTS_SPEAKERS_MD` pointing at this `speakers.md` (or rely on the script default path). In-body **CDN** portraits use the same **HTML `img` + max 300px longest side** rule as parent speaker `README.md` files (Manchester 2025 uses the identical convention). This folder may be **gitignored**; see the Artifacts repo `.gitignore`. Details: **mctsummiteu** skill `mct-summit-eu-artifacts-speakers`. **Catch-up:** `migrate_artifacts_cdn_portraits_to_html.py` with path `.../2026-sarajevo-ba` converts any legacy `![]()` CDN images to the HTML form.

## Speakers without a public speakers.run.events directory

Listed here for tracking when no directory page exists (other than name-only or event-sourced readmes as above). Session folders under their `givenname-surname/` path are unchanged.

_(none)_
