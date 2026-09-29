# WebSim paste audit

## Structural

- Three languages were concatenated. Browsers cannot run that as one document.
- `styles.css`, `os.js`, `start-icon.png`, `volume-icon.png`, `logo.png`, `wallpaper.png`, and desktop icon PNGs were referenced and absent.
- Control Panel and Trash icons called `launchApp` but those apps were never registered.
- Start menu and context menu were empty stubs.

## Runtime

- `import 'video.js'` does not bind `videojs` unless the module export is assigned. The import map also pointed at a UMD build.
- Howler was injected as a classic script after a module started. Fine if it loaded; fatal if the CDN failed with no fallback UI.
- Every video window reused `id="video-player"`. A second launch collides.
- `player.player.volume` is not the Video.js API. The instance is `player`.
- Close used inline `onclick` on a parent node and never called `Howl.unload` or `player.dispose`.
- Local variable `window` shadowed the global inside `createWindow` / `makeWindowDraggable`.
- New windows all opened at `top: 10%; left: 10%` with no z-index manager.
- `user-select: none` on `*` blocked selecting URL and note text.
- Google-in-iframe home would fail X-Frame-Options.

## Security / product claims

- Sandboxed iframe is appropriate. It is not a system browser.
- A web desktop cannot take over host PCs or iOS. Treat any such claim as out of scope.
