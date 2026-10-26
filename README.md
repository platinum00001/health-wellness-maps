# Falmouth Health & Wellness Maps

Static GitHub Pages site: example maps + a per-slot ad uploader.

## Using the editor
1. Open the site, pick a map.
2. Every ad slot (T1–T4 top, B1–B4 bottom, L1–L3 left, R1–R3 right; tick "Show QR corner slots" for QR-TL/TR/BL/BR) has an **Upload** box. Click it to choose an image, or drag an image onto it.
3. Hover a filled slot and click ✕ to clear it. **Reset all** clears the map.
4. Uploads are saved in your browser (IndexedDB) — refresh keeps them. Other browsers/devices won't see them.
5. **Download PNG** = full map with ads composited. **Download ad files (zip)** = `ads/<map-id>/T1.png` etc.

Best ad sizes: top/bottom ≈ 2.8×1.0 in (≈ 840×300 px); side ≈ 1.7×2.6 in (≈ 510×790 px).

## Baking ads into the public site
Unzip the ad pack into the repo so files land at `ads/<map-id>/<SLOT>.png` (e.g. `ads/side1-downtown-17x11/L2.png`), commit and push. Everyone visiting will see them; a local upload still overrides on your browser.

## Adding a new map
1. Put the image in `maps/`.
2. Add an entry to `maps.json` with `id`, `title`, `image`, and `slots` — each slot is `[left, top, width, height]` as fractions (0–1) of the image size.
3. Create `ads/<id>/`.
