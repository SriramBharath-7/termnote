# termnote — desktop app (Electron)

This is a real desktop app version of termnote — runs as its own window
on Windows, macOS, or Linux, no browser needed. Verified to install and
launch correctly.

## Run it (development mode)

You need [Node.js](https://nodejs.org) installed once. Then, in this folder:

```
npm install
npm start
```

A window opens with the app — same notepad, same features (Markdown
preview, image paste, themes, fonts), just running natively.

## Build an installable app (.exe / .dmg / .AppImage)

```
npm install
npm run dist
```

This produces, inside a new `dist/` folder:
- **Windows** → `termnote Setup <version>.exe` (installer)
- **macOS** → `termnote-<version>.dmg`
- **Linux** → `termnote-<version>.AppImage`

Important: **electron-builder can only reliably build for the OS you run
it on** — build the Windows installer on Windows, the macOS one on a Mac,
and so on. Cross-building (e.g. making a `.dmg` from Windows) needs extra
tooling and code-signing setup that's out of scope here.

Double-click the installer it produces, and it installs like normal
desktop software — Start Menu / Applications folder / Desktop icon
included.

## Notes

- Notes are saved locally on your machine via the browser storage layer
  Electron uses under the hood — nothing leaves your device.
- The in-app command palette (`Ctrl/Cmd+K`) still has everything: theme
  switching, fonts, Markdown toggle, save as `.txt`/`.md`/`.html`.
- If you want to change the icon later, replace `icon.png` (any square
  PNG works) and `icon.ico` (Windows needs this specific format — you can
  regenerate it from a PNG with a free tool like https://icoconvert.com).
