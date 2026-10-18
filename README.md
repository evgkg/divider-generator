# Divider Generator

A static, browser-only **RU/EN** STL generator for interlocking drawer dividers. No backend, dependencies, or build tools required. Deployable to GitHub Pages as a single `index.html`.

## Features

- Creates **internal dividers only**. No outer walls and no floor.
- Supports small drawers (e.g. 49 mm wide) with adjustable dimensions, grid rows/columns, plate thickness and slot clearance.
- Optional **trapezoidal profiles**, configured using the **bottom edge length** of each plate type. The top edge lengths come from the drawer width/depth inputs.
- Rounded bottom corner reliefs for the drawer-to-floor fillets. **Bottom reliefs additionally shorten the actual contacting edge** beyond the configured trapezoid bottom length.
- Custom rectangular **3D printer bed size**, including 220 × 220 mm by default.
- Scaled SVG bed preview of the **actual cutout profiles**, packed into a compact centered group with optional 90° rotations, 3 mm spacing, and an adjustable edge clearance (10 mm by default).
- Clearly reports how many parts fit; disables whole-set STL download when it cannot fit on the selected bed.
- Binary STL export for the entire set or each divider type, using the same 2D arrangement as the bed preview.
- Bilingual UI; saves your selected language in browser local storage when available.

## Launch

Open `index.html` in any modern web browser. All logic runs offline and locally.

## GitHub Pages

1. Create a repository (e.g. `divider-generator`).
2. Upload `index.html` to the root directory.
3. In **Settings → Pages**, select deployment from the `main` branch and `/ (root)`.
4. Open `https://<username>.github.io/divider-generator/`.

## Important details

- Input drawer width/depth are the **top plate lengths**, not separate nominal drawer dimensions plus a clearance field. Enter slightly smaller sizes if you need loose fit.
- With trapezoids enabled, specify longitudinal and transverse *bottom edge lengths* independently. Bottom rounded reliefs remove extra corner material.
- Interlocking plates use half-height slots. Adjust clearance for your printer and material.
- Set **bed edge clearance** to reserve a safe margin on all four sides. This margin is applied both to the packing algorithm and to exported STL coordinates. For clamps, forbidden zones, skirt/brim, etc., increase the margin or enter a smaller usable bed size.
- When a complete set does not fit, its export is disabled; exporting longitudinal and transverse pieces individually may still work.
- The packer tries multiple packing widths and centers the resulting group. It does not guarantee the mathematically optimal layout. If it reports overflow, a different arrangement in the slicer may still fit.

## License

MIT; see `LICENSE`.
