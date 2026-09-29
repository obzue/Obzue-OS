# Obzue OS desktop

Product mode, not marketing mode. The work surface is the desktop. Chrome stays thin.

## Visual direction

- Subject — night lab desktop for ObzueAI product work
- Palette — ink `#0b1220`, paper `#e8eef7`, seal `#3d8bfd`
- Type — system UI sans for chrome, tabular figures for the clock
- Memorable element — one seal glyph in the start button. No second mascot

## Required apps

- Assistant — chat log plus honest capability list
- Notes — localStorage pad
- Audio — Howler, object URL, dispose on close
- Video — Video.js, unique element id, dispose on close
- Zue Browser — URL bar, history, iframe with sandbox. Default home is a same-origin help page.
- Control Panel — clock format, reduce motion
- Trash — list of dismissed icons, restore

## Window manager contract

Each window object holds `{ id, title, el, appId, z, onClose }`.
Focus raises z. Drag from header only. Close runs onClose then removes the node.
New windows offset by `16px * (openCount % 8)`.

## Asset policy

Prefer inline SVG. Do not depend on missing PNGs.

## Checks

Desktop visible after boot. Icons launch windows. Start and context menus work. Second video window does not steal the first player. Closing audio stops playback. Inputs accept selection.
