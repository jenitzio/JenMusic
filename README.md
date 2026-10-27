# JenMusic

**A browser-based techno production workstation with a built-in drum machine, acid sequencer, and audio-editing timeline.**

JenMusic is a music-making project by [jenitzio](https://github.com/jenitzio). Its interface is styled like a compact, dark digital audio workstation (DAW), with high-contrast neon accents and controls designed around electronic music production.

The app can run as a web page and includes an Electron desktop wrapper for packaging it as a desktop application.

> **Project status:** In development. Features and compatibility may change as the project evolves.

## Features

### Audio arrangement and editing
- Import audio files, including WAV, MP3, OGG, FLAC, M4A, and AAC through the file picker (actual decoding support depends on the browser or Electron runtime).
- Arrange audio clips across a multi-track timeline.
- Move and trim clips, with optional grid snapping and adjustable timeline zoom.
- Split clips at the playhead or use the razor tool.
- Duplicate, merge, stitch, reverse, normalize, and apply automatic fades to selected clips.
- Undo and redo editing operations.
- Adjust track volume, pan, filtering, mute, and solo controls.

### Techno drum and acid sequencer
- Program a step-based drum and acid pattern.
- Adjust pattern length from 1 to 16 bars.
- Control swing and audition the pattern before rendering it to a timeline track.
- Start from included pattern presets or randomize a pattern.
- Shape the kick and bass sounds with controls such as tuning, decay, drive, rumble, filter cutoff, resonance, and envelope modulation.
- Click instrument row names to audition sounds; use step accents for extra emphasis.

### Mix and export
- Set the project tempo (BPM), loop playback, and use the transport controls.
- Shape the master output with volume, glue compression, tempo-synchronised delay feedback, and a limiter.
- View the built-in spectrum display.
- Export the rendered mix as a WAV file.

## Getting started

### Option 1: Run in a browser

The core interface is in `index.html` and uses browser audio APIs. From the project directory, start a local static server:

```bash
python3 -m http.server 8000
```

Then open **http://localhost:8000** in a modern browser.

You can also open `index.html` directly, but a local server is generally more predictable for browser-based projects.

### Option 2: Run the Electron desktop app

The repository includes `main.js` and a `package.json` configured for Electron.

1. Install a current Node.js LTS release and npm.
2. From the repository directory, install the project dependencies:

   ```bash
   npm install
   ```

3. Launch the app:

   ```bash
   npx electron .
   ```

The Electron window loads the local `index.html` file. The package configuration also declares Electron Builder targets for Linux AppImage and Windows portable builds; packaging can be attempted with:

```bash
npx electron-builder
```

Build output and platform-specific prerequisites may vary. The package currently does not define custom npm scripts.

## Controls

Some useful keyboard shortcuts shown in the interface:

| Shortcut | Action |
| --- | --- |
| `Space` | Play / pause |
| `V` | Select / move tool |
| `C` | Razor / split tool |
| `S` | Split selected clip at the playhead |
| `M` | Merge selected clips |
| `J` | Stitch selected clips |
| `Ctrl+ D` | Duplicate |
| `Ctrl+ Z` | Undo |
| `Ctrl+ Y` | Redo |
| `Delete` | Delete selection |
| `+` / `-` | Zoom in / out |

Keyboard shortcuts and browser behaviour may differ across operating systems.

## Compatibility and notes

- Use a modern browser with Web Audio API support, or run the included Electron wrapper.
- Audio import and decoding depend on runtime support for the selected format.
- Export time and performance depend on the length of the arrangement and the computer.
- Keep backups of important projects and source audio while the app is under development.
- This README describes controls visible in the current interface; it is not a guarantee that every workflow has been exhaustively tested.

## Development

The current repository includes:
- `index.html` — interface, styling, and the main application logic.
- `main.js` — Electron entry point.
- `package.json` — package metadata and desktop build configuration.

There is no separate build step required to serve the web interface.

## Contributing

Bug reports, suggestions, and improvements are welcome. When reporting an issue, include:
- Your operating system and browser or Electron version.
- Steps to reproduce the problem.
- Any relevant console errors.
- A brief description of the audio file type or project setup involved (avoid sharing private audio unless you intend to).

## License

JenMusic is distributed under the **Apache License 2.0**. See [LICENSE](LICENSE) for the full license text.
