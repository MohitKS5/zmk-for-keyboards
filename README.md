# Corne ZMK Keymap

Split ergonomic keyboard (42 keys) running [ZMK firmware](https://zmk.dev) on Nice!Nano v2.
Miryoku-style layout adapted from TOTEM config.

## Keymap

Auto-generated from [`config/corne.keymap`](config/corne.keymap) via [keymap-drawer](https://github.com/caksoylar/keymap-drawer):

![Keymap](corne_keymap.svg)

The SVG updates automatically on push via the [Draw Keymap](.github/workflows/draw-keymap.yml) workflow.

## Deviations from Miryoku

1. **SYM: Pascal Getreuer's symbol layout**
   a. Two-handed symbols instead of Miryoku's one-handed left
   b. Right home row keeps `&hmr` mods for cross-hand use
2. **NAV: ESDF inverted-T arrows**
   a. UP on top row (pos 8), LEFT/DOWN/RIGHT on home row (pos 19/20/21)
   b. Replaces Miryoku's HJKL all-on-home-row layout
   c. Undo moved to pos 18 (below redo) to make room for UP on top row
   d. Clipboard stays on NAV: redo(6), paste(7), UP(8), copy(9), cut(10), undo(18)
3. **MOUSE: ESDF inverted-T movement**
   a. Same spatial pattern as NAV for mouse movement
   b. Scroll keys on bottom row
4. **MEDIA: no RGB, repurposed slots**
   a. RGB replaced with brightness (C_BRI_DN/UP), lock (Ctrl+Cmd+Q), Ctrl+Space on right top row
5. **All GUI shortcuts → Ctrl**
   a. `LC()` instead of `LG()` throughout combos and layers

## Display

- **Left (central):** Built-in ZMK status screen (layer, battery, BT)
- **Right (peripheral):** Custom P keycap logo with glitch effects + battery + BT status

## Interactive Viewer

```sh
make viewer
```

Press `?` for the cheat sheet. Press `0-6` to switch layers.

## Bootloader

To enter flashing mode without opening the case, press the **4 outer top-row keys** simultaneously (keyboard must be idle for 2 seconds):

- **Left half:** TAB + Q + R + T (positions 0, 1, 4, 5)
- **Right half:** Y + U + P + BSPC (positions 6, 7, 10, 11)

Each half must be flashed separately.

## Build Firmware

Push to `config/` or `build.yaml` triggers the [Build ZMK firmware](.github/workflows/build.yml) workflow. Download `.uf2` files from Actions artifacts.

## Regenerate Keymap SVG

```sh
make install   # one-time: pip install keymap-drawer
make svg       # parse + render SVG
```

## Hardware

- **Board:** Nice!Nano v2 (nRF52840)
- **Shield:** Corne (split, 6x3+3)
- **Display:** OLED SSD1306 128x32 / Nice!View
- **Bluetooth:** 4 profiles
- **ZMK Studio:** Enabled
- **Mouse/Pointing:** Enabled
