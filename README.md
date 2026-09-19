# show

A minimal media browser for images and videos. Single HTML file, no server, no uploads — everything stays local.

**Live:** [47096.github.io/show](https://47096.github.io/show/)

## Features

- **Unified gallery** — images and videos in one masonry wall (true aspect ratios, generous gutters)
- **Image viewer** — dark theatre chrome; zoom 25–500%, drag-to-pan, double-click 100%↔200%, slideshow
- **Video player** — keyboard seek (±5s), Shift+arrows for clips, loop modes, A-B repeat, speed, shuffle, PiP, fullscreen
- **Type filter** — All / Images / Videos
- **Search & sort** — path + name, date, size, type, duration, resolution
- **Select mode** — shift+click ranges; move to folder; quiet “remove from view” vs filled “delete from disk” (path-aware; nested folders work)
- **Theme** — follows `prefers-color-scheme`; manual toggle saved in `localStorage`
- **Keyboard-first** — shortcuts overlay (`?`); inline SVG icons on chrome
- **Drag & drop** — files or folders, recursive scan
- **Large folders** — batched grid + video thumbs as object URLs (not base64)
- **UI** — instrument header (folder identity, inset search), teaching empty states, light-table selection marks

## Supported formats

**Images:** JPG, PNG, GIF, WebP, BMP, SVG, AVIF, TIFF  
**Videos:** MP4, WebM, OGG, MOV, M4V are the reliable set. MKV, AVI, FLV, WMV may appear in the grid but playback depends on the browser’s codecs — don’t assume they will play.

## Usage

**Best:** open the [GitHub Pages build](https://47096.github.io/show/) in **Chrome or Edge**.

**Local full functionality** (folder open / move / delete need the File System Access API):

```bash
cd show
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

Opening `index.html` via `file://` can browse after drag-drop, but folder write APIs are limited — prefer HTTP.

**Folder operations:** Chrome/Edge + **Open Folder** (not drag-drop) for move/delete-from-disk. Drag-drop is browse/remove-from-view only.

## Keyboard shortcuts

| Key | Gallery | Image Viewer | Video Player |
|-----|---------|--------------|--------------|
| `S` | Select mode | — | — |
| `F` | Open folder | — | Fullscreen |
| `Shift+click` | Select range | — | — |
| `⌘/Ctrl+click` | Toggle card | — | — |
| `?` | Shortcuts | — | — |
| `←` `→` | Navigate cards | Prev/Next image | Seek ∓5s |
| `Shift+←` `→` | — | — | Prev/Next video |
| `Home` `End` | — | — | Start / end of clip |
| `↑` `↓` | — | Zoom in/out | — |
| `0` | — | Reset zoom & pan | — |
| `drag` | — | Pan when zoomed | — |
| `dbl-click` | — | 100% ↔ 200% | — |
| `Space` | — | — | Play/Pause |
| `M` | — | — | Mute |
| `[` `]` | — | — | A-B repeat |
| `Esc` | Exit select | Close viewer | Close player |

## Design

- **Chrome / controls / paths:** IBM Plex Mono
- **Prose** (landing copy, empty states, toasts): IBM Plex Sans
- **Icons:** inline SVG (24 viewBox, ~1.75 stroke) — no unicode control glyphs
- **Accent:** `#3b82f6`; danger for permanent delete only
- **Theme:** OS preference when unset; toggle saved in `localStorage`
- **Media wall:** masonry `column-width: 220px`, ~10px gutters, no card shells; hover = inset hairline (no lift/shadow); select = accent ring + order chips
- **Header:** instrument strip (~48px) with `show · folder`, inset search, underline type filter, quieter secondary tools
- **Image viewer:** always dark theatre backdrop; control language matches the video player
- **Landing:** full-viewport stage, ghost masonry, large wordmark — no dashed upload hero
- All client-side, zero dependencies
- Single `index.html`

## License

[MIT](LICENSE)
