# ZMK Corne Keyboard Layout

This this my personal [zmk](https://github.com/zmkfirmware/zmk) config for my
[corne keyboard](https://github.com/foostan/crkbd).
I have the Corne Chocolate v2.1 board, and some nice 3d printed [Cases](https://www.printables.com/model/624445-tented-corne-keyboard-case).

I initialy cloned DarrenVictoriano`s [Reop](https://github.com/DarrenVictoriano/zmk-config), but I ended up changing a lot!

Special about my build:
- I don't use BT, just USB
   - both sides communicate via TRS Cable
   - no need to rely on battery
   - no lag, bad connection or sleepy keyboard
- Special German Layout
   - de-DE on OS level

The firmware is built to
work with the following devices:

- Keyboard: Corne 6 column
- Controller: ProMicro nRF52840 (nice!nano v2 clone)

## Keymaps

These are the keymaps and layers defined in this config. The keymaps were
generated using
[Nick Coutsos's Keymap Editor](https://nickcoutsos.github.io/keymap-editor/).

![keymaps](https://github.com/Greqory/zmk-config/blob/master/images/corne.svg)

**Macros**

- ⚡️ : hyper key (`ctrl` + `shift` + `alt` + `cmd`)
- ⚙️ : system settings (`cmd` + `shift` + `J`)
- 📷 : `printscreen` (linux) / `F13` (macos)
- 🖥️ : TTY for linux (`ctrl` + `cmd` + `F2`)
- `⌘⌥⎵` : homerow / hints
- `⌃⎵` : tmux leader key

> The image is generated using
> [Cem Aksoylar's Keymap-drawer](https://github.com/caksoylar/keymap-drawer)

## Installing Firmware

Whether you built it yourself or downloaded my prebuilt firmware, it should
contain the following files:

- nano_corne_left.uf2
- nano_corne_right.uf2
- nano_reset_settings.uf2

> The `*_reset_settings.uf2` file is used to clear persistent settings like
> default layers, BLE pairings, and other saved data that may remain after
> repeatedly flashing new firmware.

### Steps

1. Plug in your left Corne keyboard (it doesn't need to be turned on).
2. Double-press the side button to enter bootloader mode.
3. Copy `nano_reset_settings.uf2` to the keyboard's root folder.
4. After the error appears, unplug and replug the keyboard.
5. Double-press the button again to go back into bootloader mode.
6. Copy `nano_corne_left.uf2` to the device. (Make sure to use the correct left
    firmware!)
7. Unplug after the error, then repeat steps 1–6 for your right Corne using
    `nano_corne_right.uf2
8. Make sure both are unplugged. Connect both boards with TRS cable.
9. Connect left board with USB, and use your keyboard. Enjoy!
