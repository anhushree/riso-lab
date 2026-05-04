# Riso Lab 🎨

A browser-based risograph print effect studio. No install, no account, no backend.

## Deploy to Vercel

1. Go to vercel.com → New Project
2. Drag this entire folder into Vercel
3. Done — live at `*.vercel.app`

Or via GitHub:
1. Push this folder to a GitHub repo
2. Connect to Vercel → auto-deploys on every push

## Files

- `index.html` — the entire app (single file)
- `vercel.json` — sets required headers for ffmpeg.wasm (MP4 export)
- `README.md` — this file

## Features

- 5 render modes: Riso, Riso+Dither, Riso+Grain, Riso+Floyd, Riso+ASCII
- Figma-style colour picker
- Original colour extraction (k-means)
- Saved palettes (localStorage)
- Video live preview
- Frame export (ZIP of PNGs → encode to MP4 with ffmpeg)

## Encode exported frames to MP4

After exporting frames ZIP, run:
```
ffmpeg -framerate 30 -i frame_%04d.png -c:v libx264 -pix_fmt yuv420p output.mp4
```

## Stack

Pure HTML + Canvas API + Vanilla JS. Zero dependencies except JSZip (CDN).
