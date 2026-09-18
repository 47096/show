# show

A minimal media browser for images and videos. Single HTML file, no server, no uploads — everything stays local.

## Features

- **Unified gallery** — images and videos in one grid
- **Image viewer** — zoom (25%–500%), slideshow with adjustable speed
- **Video player** — seek, volume, loop modes, A-B repeat, playback speed, shuffle, PiP, fullscreen
- **Type filter** — All / Images / Videos toggle
- **Search & sort** — by name, date, size, type, duration, resolution
- **Select mode** — multi-select with move to folder, remove, delete from disk
- **Dark mode** — toggle with localStorage persistence
- **Keyboard navigation** — arrow keys, Enter/Space, shortcuts overlay (`?`)
- **Drag & drop** — files or entire folders, recursive scan
- **Virtual scroll** — smooth performance with large folders
- **Mobile friendly** — touch targets, swipe navigation, responsive grid

## Supported formats

**Images:** JPG, PNG, GIF, WebP, BMP, SVG, AVIF, TIFF
**Videos:** MP4, WebM, OGG, MOV, MKV, AVI, M4V, FLV, WMV

## Usage

Open `index.html` in Chrome or Edge (File System Access API required for folder operations).

For full functionality, serve over HTTP:

```bash
cd show
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Keyboard shortcuts

| Key | Gallery | Image Viewer | Video Player |
|-----|---------|--------------|--------------|
| `S` | Select mode | — | — |
| `F` | Open folder | — | Fullscreen |
| `?` | Shortcuts | — | — |
| `←` `→` | Navigate cards | Prev/Next image | Prev/Next video |
| `↑` `↓` | — | Zoom in/out | — |
| `Space` | — | — | Play/Pause |
| `M` | — | — | Mute |
| `[` `]` | — | — | A-B repeat |
| `Esc` | Exit select | Close viewer | Close player |

## Design

- Font: IBM Plex Mono
- Accent: #3b82f6
- All client-side, zero dependencies
- Single `index.html` file (~1200 lines)
