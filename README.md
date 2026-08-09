# tf2UnusualIds

JSON datasets mapping Team Fortress 2 **Unusual** particle effect IDs to their names, for hats (cosmetics), taunts, and weapons.

## Categories

| Category | ID range | Count |
|---|---|---|
| Hats (cosmetics) | 0–378 | 363 |
| Taunts | 3001–3201 | 199 |
| Weapons | 701–704 | 4 |
| All (combined) | — | 566 |

Each category has 4 files, and there's a combined `all_*` set covering every category together:

- `<category>_simple.json` — `{ "Effect Name": id, ... }`
- `<category>_simple_reversed.json` — `{ "id": "Effect Name", ... }`
- `<category>_full.json` — `{ "Effect Name": { "id": id, "wiki_link": url }, ... }`
- `<category>_full_reversed.json` — `{ "id": { "name": "Effect Name", "wiki_link": url }, ... }`

`wiki_link` points to the effect's image file page on the [official TF2 wiki](https://wiki.teamfortress.com/wiki/Unusual) (e.g. `https://wiki.teamfortress.com/wiki/File:Unusual_Burning_Flames.png`). It's `null` for a handful of entries that aren't real documented effects (unused/debug particle slots) or that are too new to be on the wiki yet.

## Team-colored effects

Some Unusual effects render differently for RED and BLU and use two separate effect IDs — one per team. These appear as two entries sharing a base name, disambiguated with a suffix, e.g.:

```json
"Aces High (RED)": 55,
"Aces High (BLU)": 59
```

## Example

```json
// hats_full.json
{
  "Burning Flames": {
    "id": 13,
    "image_link": "https://wiki.teamfortress.com/wiki/File:Unusual_Burning_Flames.png"
  }
}
```

## Source

Effect IDs were supplied manually; names were cross-checked and wiki links were resolved against [wiki.teamfortress.com](https://wiki.teamfortress.com/wiki/Unusual).
