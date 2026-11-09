# Roger Wilco Imagery — Ottawa Watch (baseline imagery)

Open baseline satellite imagery for the **Ottawa Watch** of [Roger Wilco Imagery](https://rogerwilcoimagery.com) (RWI), a project of
Prime Rogue Inc. RWI watches the main buildings of every Canadian federal entity in the National Capital Region from open sources.
This repository is the public record of the clear-sky reference images that RWI compares new passes against.

**Imagery:** 32 clear Sentinel-2 quicklooks across 8 places, July–October 2026.

## What is here

| Place | Id | Box (W, S, E, N) | Images | Dates | On the site |
|---|---|---|---|---|---|
| Confederation Heights | `ott-campus-confederation-heights` | -75.697, 45.372, -75.678, 45.386 | 4 | 2026-07-20 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-campus-confederation-heights.html) |
| NRC Montreal Road campus | `ott-campus-nrc-montreal-road` | -75.629, 45.442, -75.605, 45.456 | 4 | 2026-07-20 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-campus-nrc-montreal-road.html) |
| CSE / CSIS Ogilvie Road cluster | `ott-campus-ogilvie-intel` | -75.622, 45.431, -75.609, 45.440 | 4 | 2026-07-16 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-campus-ogilvie-intel.html) |
| Place du Portage I-IV | `ott-campus-place-du-portage` | -75.724, 45.425, -75.713, 45.432 | 4 | 2026-07-11 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-campus-place-du-portage.html) |
| Les Terrasses de la Chaudiere | `ott-campus-terrasses-chaudiere` | -75.725, 45.423, -75.717, 45.428 | 4 | 2026-07-11 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-campus-terrasses-chaudiere.html) |
| Tunney's Pasture | `ott-campus-tunneys-pasture` | -75.742, 45.398, -75.726, 45.407 | 4 | 2026-07-11 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-campus-tunneys-pasture.html) |
| Ottawa downtown core (Parliament, Wellington, Sparks, Laurier) | `ott-downtown-core` | -75.714, 45.414, -75.688, 45.429 | 4 | 2026-07-11 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-downtown-core.html) |
| Gatineau federal district (Place du Portage, Terrasses de la Chaudière, 30 Victoria) | `ott-gatineau-core` | -75.727, 45.422, -75.710, 45.433 | 4 | 2026-07-11 → 2026-10-29 | [place page](https://rogerwilcoimagery.com/place/ott-gatineau-core.html) |

The Ottawa Watch lists 65 places. The other 57 are single buildings inside the 8 campuses and zones above; they share those images
rather than getting their own (a Sentinel-2 pixel is 10 m, too coarse for a building on its own).

- `baselines/<place>/baseline_s2_<date>_<scene>_rgb.jpg`: true-colour quicklook (Sentinel-2 L2A, bands 4-3-2).
- `baselines/<place>/…_rgb.json`: georeference sidecar (CRS, bounds in that CRS, pixel size).
- `index.json`: every image with its scene id, acquisition time (UTC), cloud and clear-sky fractions, and how it was cloud-masked.

## How the images are made

RWI's baseline backfill picks a few clear scenes per place from the past year (four per place as of this sync), newest first and at least 30 days apart. A scene
qualifies only if it covers the place and the scene classification and RWI's own cloud mask both find it clear. The tiles of one
acquisition are mosaicked when a place straddles them. Source: Sentinel-2 L2A from Element 84 Earth Search and Microsoft Planetary
Computer. The quicklooks are for the eye: no raw GeoTIFFs, so they are not used for RWI's change scores.

All times are UTC.

## Licence and attribution

- **Imagery and index (RWI Materials):** see [LICENSE-IMAGERY.md](LICENSE-IMAGERY.md). Underlying data: Copernicus Sentinel, free to
  reuse with attribution. Please credit: **"Contains modified Copernicus Sentinel data 2026, processed by Roger Wilco Imagery."**
- **Code** (if any is added here): MIT, see [LICENSE](LICENSE).

Updated by RWI when new baselines are made. Questions and corrections: via [rogerwilcoimagery.com](https://rogerwilcoimagery.com).
