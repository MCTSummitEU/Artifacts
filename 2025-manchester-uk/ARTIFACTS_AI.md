# 2025 Manchester — AI / maintainer notes

**Audience:** AI agents and repo maintainers. The public **[README.md](README.md)** is intentionally minimal.

This tree mirrors the [agenda](../../content/2025-manchester-uk/agenda.md). Public schedule and copy: [European MCT Summit 2025 on run.events](https://e.runevents.net/european-mct-summit-2025). Each leaf session folder is where slides and examples go. Session-level `README.md` files can hold title, speaker list, and abstract from the API.

## Naming

- **Per person:** `givenname-surname` (kebab-case, e.g. `jonah-andersson`, `marc-michault`, **Andreas Schlüter** → **`andreas-schlueter`** — ü is **`ue`**, not a single `u`). If that person has **no** session linked 1:1 to run.events yet, prefix the speaker folder with **`_`** (if you use the placeholder convention).

- **Cohosted sessions (agenda lists multiple people):** one folder, **alphabetical order by family name**; for each person `givenname-surname`, concatenated. (Existing trees may have been created before this rule; new folders should follow it.)

- **Panels:** same as cohosted. If the public agenda only lists a moderator, you may use `{givenname-surname}-and-copanelists/{session-slug}/` and rename to the full name chain when the panelist list is complete.

- **Same speaker twice:** two session folders under the same `givenname-surname/`.

- **Solo folder only if needed:** create **`givenname-surname/`** when that speaker has **at least one** solo (non–co-hosted) session artifact tree. If they appear **only** in co-hosted or panel sessions, **do not** create a solo folder — their bio and profile live only in the combined parent `README.md`.

## Session slugs

Session folders use short kebab-case slugs (no dates), stable when you tweak titles slightly.

- **Not matched to run.events (1:1):** optional **`_`** prefix on speaker or session folder (match your tracking), as in the [2026 Sarajevo](../2026-sarajevo-ba/ARTIFACTS_AI.md) tree.

## Per-speaker README

In `{givenname-surname}/README.md` (solo speakers):

- **Title** `# {GivenName SurName}` (match the site), then **portrait** as an HTML **`<img>`** pointing at `https://cdn.runevents.net/speaker-profile-images/{uuid}` with **max 300px on the longest side** (see `scripts/artifacts_speaker_portrait.py` in the skill), then **bio** (from API or event UI).
- **End of file:** `{GivenName SurName}: [Speaker profile](https://speakers.run.events/… ) on run.events` — link text is **Speaker profile**; the trailing **on run.events** is the platform name. For **Sessionize**-only events, use the same pattern with **on Sessionize** and the Sessionize profile URL. If there is no public directory, link **Speaker profile** to the in-app listing (e.g. event speakers page).
- **Regenerate** all **parent** `README.md` files from the API: in **mctsummiteu** run `scripts/build_manchester_artifact_readmes.py` (see skill `mct-summit-eu-artifacts-speakers`). This matches the Sarajevo pattern (slim solo READMEs like `dmitrii-solovev/README.md`). It does not overwrite `…/<session-slug>/README.md` session stubs.

Session materials stay in `{givenname-surname}/{session-slug}/` as usual.

## Co-hosted and panel parent folders

- **Parent `README.md` (`givenname-...-givenname/README.md`):** use **one `# Speaker full name` block per person** (H1). For each: portrait `![…](CDN)` where available, full **inline** biography, then `{Name}: [Speaker profile](…) on run.events`. **Do not** link to `../givenname-surname/README.md` for speakers who have no solo folder.

- Reference (Sarajevo, same convention): [../2026-sarajevo-ba/amelia-hernandez-osorio-andre-thiemann/README.md](../2026-sarajevo-ba/amelia-hernandez-osorio-andre-thiemann/README.md)

## Optional `_speakers/speakers.md` and profile screenshots

- **Path:** `_speakers/speakers.md` — generated list of speakers from the run.events API (one `#` block per person, same footer pattern as solo READMEs). **Front matter** includes `event_slug` and source API URLs. **Regenerate** from the mctsummiteu repo with `build_speakers_md.py`, setting `MCT_RUNEVENTS_EVENT=european-mct-summit-2025` and `MCT_ARTIFACTS_SPEAKERS_MD` to this file’s full path. Default script settings target Sarajevo 2026 unless you override.
- **Screenshots:** the same `_speakers/` directory may contain **`*.png`** captures of each speaker on `speakers.run.events` (e.g. browser saves with a date/time in the name). They are **not** wired into the markdown; match to a speaker by **name** when auditing. In-body images in `speakers.md` use the **CDN** URL from the API.
- The **`_speakers/`** tree is listed in the Artifacts repo **`.gitignore`** (local / optional check-in policy).

## APIs (run.events)

- **This event** `eventSlug` for the dashboard API: `european-mct-summit-2025`
- Speakers: `https://api.runevents.net/api/event-dashboard/speakers?eventSlug=european-mct-summit-2025`
- Sessions: `https://api.runevents.net/api/event-dashboard/sessions?eventSlug=european-mct-summit-2025`

## Speakers without a public speakers.run.events directory

List here for tracking when no directory page exists. Session paths under their `givenname-surname/` are unchanged when applicable.

_(none)_
