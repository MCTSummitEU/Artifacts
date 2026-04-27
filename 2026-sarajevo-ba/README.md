# 2026 Sarajevo — speaker artifacts (placeholder tree)

This tree mirrors the [agenda](../../content/2026-sarajevo-ba/agenda.md). Each leaf session folder is where slides and examples go; nothing is in here yet.

## Naming

- **Per person:** `givenname-surname` (kebab-case, e.g. `jane-doe`, `nicky-de-westelinck`, `michael-kirst-neshva`). If that person has **no** session linked 1:1 to run.events yet, prefix the speaker folder with **`_`** (e.g. `_eltjo-van-gulik`).

- **Cohosted sessions (agenda lists multiple people):** one folder, **alphabetical order by family name**; for each person `givenname-surname`, concatenated. Example: `damir-dizdarevic`, `robert-hales`, `jasmin-kahriman`, `rolf-mclaughlin` (D → H → K → Mc) →
  `_damir-dizdarevic-jasmin-kahriman-robert-hales-rolf-mclaughlin/_opening-session-and-keynote/` (leading `_` on the speaker folder when none of their sessions are matched 1:1 to run.events, and `_` on each unmatched session slug).
  and `amelia-hernandez-osorio-andre-thiemann/.../`.

- **Panels (like cohosted, same idea):** if the [public agenda](https://e.runevents.net/mct-eu-summit-2026) only lists a moderator, use **`{givenname-surname}-and-copanelists/{session-slug}/`**. Add full panelist names in that folder’s `README.md` (and in the [agenda](../../content/2026-sarajevo-ba/agenda.md) when confirmed). You can **rename** the cohost folder to the full `givenname-surname-...-givenname-surname` chain when you have a complete list.

- **Same speaker twice:** two session folders under the same `givenname-surname/`.

## Session slugs

Session folders use short kebab-case slugs (no dates), stable when you tweak titles slightly.

- **Not matched to run.events (1:1):** prefix the session folder name with **`_`** (e.g. `_johan-smarius/_storytelling-for-trainers`: underscore on the speaker parent when they are still “absent” from the API mapping, and on the session leaf).
