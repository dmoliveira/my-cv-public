# Production design sources

## Recruiter CV social card

- Source: `cv-social-card-1200x630.svg`
- Published export: `../../assets/social/diego-cv-1200x630.jpg`
- Critical text and portrait stay inside a 64 px safe zone.
- Typography uses Arial/Helvetica only; the portrait is the tracked real headshot derivative.

Reproducible export from the repository root:

1. Serve the repository on `http://127.0.0.1:4174`.
2. Open `/artifacts/design/cv-social-card-1200x630.svg` in headless Chrome with a 1200×630 viewport.
3. Capture an exact 1200×630 PNG screenshot.
4. Convert it with `sips -s format jpeg -s formatOptions 88` to the published path.

The production JPEG must be RGB, exactly 1200×630, and no larger than 400,000 bytes.

## Portrait icon derivatives

- Source: `../../assets/photos/dmz-2.png` (square, 1024×1024)
- Browser favicon: `../../assets/icons/diego-64.png`
- Apple touch icon: `../../assets/icons/diego-180.png`

Reproducible exports from the repository root on macOS:

```sh
mkdir -p assets/icons
sips -z 64 64 assets/photos/dmz-2.png --out assets/icons/diego-64.png
sips -z 180 180 assets/photos/dmz-2.png --out assets/icons/diego-180.png
sips -g format -g pixelWidth -g pixelHeight assets/icons/diego-64.png assets/icons/diego-180.png
```

Both outputs must remain square RGB PNGs at their named dimensions. They are deterministic derivatives of the tracked real portrait, not generated likenesses.
