# demi-ugc-shotsheet

Published, editable shot-sheets for Demi UGC videos. Served on GitHub Pages as one
shared app with a folder per item.

- `index.html` , the hub. Reads `reels.json` and lists every item as a card.
- `shot.html?r=<id>` , the shared editable shot-sheet app. Loads `reels/<id>/data.json`,
  prefixes frame paths with `reels/<id>/`, and Saves back to `reels/<id>/data.json` via
  the GitHub Contents API using a fine-grained token (Contents: Read and write) pasted
  once into the page (stored in localStorage; the same token works for every item).
- `reels.json` , registry of all items.
- `reels/<id>/data.json` + `reels/<id>/frames/` , per-item data and reference frames.

Items are created by `automation/process-reel.js` in the parent project
(`demi-ugc-automation`), which scaffolds a live draft; the script is then written in a
Claude session per `automation/CREATIVE-STEP.md`.

Live: https://thepmfguy.github.io/demi-ugc-shotsheet/
