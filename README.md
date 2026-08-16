# tf2UnusualIds

JSON datasets mapping Team Fortress 2 **Unusual** particle effect defindexes to their names, for hats (cosmetics), taunts, and weapons.

- GitHub: https://github.com/Franciscoborges2002/tf2-unusual-ids
- Codeberg: https://codeberg.org/fborges02/tf2-unusual-ids

## Categories

| Category | ID range | Count |
|---|---|---|
| Hats (cosmetics) | 0–415 | 354 |
| Taunts | 3001–3229 | 190 |
| Weapons | 701–704 | 4 |
| All (combined) | — | 548 |

IDs match the game's actual defindex values, verified 1:1 against the item schema. Note that RED/BLU team-colored effects (e.g. Aces High, Old Hire) share a single defindex — the wiki documents both colors as separate preview images, but there's only one effect ID per pair.

Each category has 4 files, and there's a combined `all_*` set covering every category together:

- `<category>_simple.json` — `{ "Effect Name": id, ... }`
- `<category>_simple_reversed.json` — `{ "id": "Effect Name", ... }`
- `<category>_full.json` — `{ "Effect Name": { "id": id, "image_link": url }, ... }`
- `<category>_full_reversed.json` — `{ "id": { "name": "Effect Name", "image_link": url }, ... }`

`image_link` points directly to the effect's preview image on the [official TF2 wiki](https://wiki.teamfortress.com/wiki/Unusual). It's `null` for a handful of entries that aren't real documented effects (unused/debug particle slots, defindex 0–5/20/28) or that are too new to have an image uploaded yet.

## Example

```json
// hats_full.json
{
  "Burning Flames": {
    "id": 13,
    "image_link": "https://wiki.teamfortress.com/w/images/a/ad/Unusual_Burning_Flames.png"
  }
}
```

## Source

Defindexes were sourced from the game's item schema; names and image links were cross-checked against [wiki.teamfortress.com](https://wiki.teamfortress.com/wiki/Unusual).
