# HM-Project

## A321 Tail Working Platform — interactive 3D model

`index.html` is a self-contained web viewer (Three.js, loaded from the jsDelivr CDN) that
rebuilds the scaffold platform from drawing set **A321-T001A … T007A** (Platform Design 1/7–7/7,
preliminary design) in 3D around a reference Airbus A321.

Open it by serving the folder and visiting it in a browser:

```bash
python3 -m http.server 8000
```

then go to <http://localhost:8000/>. It can also be hosted as-is on GitHub Pages
(Settings → Pages → deploy from branch, root folder).

### What's modelled

| Assembly | Size (from drawing) | Key levels |
|---|---|---|
| Main fuselage platform | 9×1800 + 1200 + 8×1800 = 31.8 m long, 1800/1500/1500/1500/1800 = 8.1 m wide | deck EL +6.048, guard to +8.048; hangs above the wing |
| Nose towers (×2) | 2×1800 × 1800, angled ~23° either side of the nose | deck EL +4.048, guard to +6.048 |
| Tail tower | grid A1–F1 (5×1800) × 1800/1800/1200/1800/1800 | 1500 lifts to +12.648 (F1 line +11.148); decks at +6.148, +8.148, +9.648, +11.148; gap for the horizontal stabiliser on A1–C1 |

Viewer features: orbit/pan/zoom, preset views matching the drawing sheets (plan, side 6-6,
front, tail 1-1), layer toggles, a section cut along the aircraft with A1–F1 presets,
click-to-inspect parts (length, elevation, BOM line), a **bill of materials**, and `.glb` export.

### Bill of materials

The **Open full BOM** button lists every component counted from the 3D model, grouped by item and size
and split per assembly (main / nose / tail), with total length or deck area. Clicking a line highlights those
parts in 3D; the table can be downloaded as CSV or copied into Excel. Standards are split into
3.0/2.5/2.0/1.5/1.0/0.5 m stock lengths as an estimate; couplers/pins, ties and wheel brakes are not listed.
A snapshot is in `model/A321_tail_platform_BOM.csv`.

`model/A321_tail_working_platform.glb` is a pre-exported copy of the model for Blender,
SketchUp, Revit, online glTF viewers, etc.

> The aircraft is a simplified reference envelope, and some details (exact deck layout per
> lift, stair positions) are interpreted from the 2D drawings. Preliminary — not for construction.
