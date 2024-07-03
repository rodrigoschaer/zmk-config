# Hillside 48 ZMK firmware

This is a more concise readme suited for Hillside 48. [Check the board developer's Readme](https://github.com/mmccoyd/zmk-config/blob/main/README.md) for a complete take.

![image](https://github.com/rodrigoschaer/zmk-config/assets/70034234/0fb8c6e4-0121-4ca6-93d1-b0fee3defa6a)

[![Build](https://github.com/rodrigoschaer/zmk-config/actions/workflows/build.yml/badge.svg)](https://github.com/FilippeMafra/hillside-zmk-config/actions/workflows/build.yml)

This is the [ZMK](https://zmk.dev/docs) firmware for the [Hillside](https://github.com/mmccoyd/hillside) family of split ergonomic keyboards.

It contains keymap definition files for the board in [./config](./config):
 - Hillside 48 with 3x6+1+5 keys

Pushing changes will build all the keyboards. You need to be signed in to a GitHub account to push changes and build the firmware. To not waste build time, comment out the keyboards in [./build.yaml](./build.yaml) that you do not have.

## Building the Firmware
- Fork this repo on GitHub
- Clone your fork locally
- Trigger a build:
  - Make a trivial change to ./build.yaml (or any non *.md file)
  - Push that change
- Look in the [Actions](https://github.com/rodrigoschaer/zmk-config/actions) tab
     for the build triggered by that change. 
- Wait for the build to finish
- Click on the build link next to the green checkbox
- Download the artifact file with the firmware
- See [Installing The Firmware](https://zmk.dev/docs/user-setup#installing-the-firmware)
  for more details from there. But a TLDR is below

## Flashing UF2 Files
- Once firmware is downloaded, extract the zip and you can verify it should contain one or more uf2 files, which will be copied to your keyboard.
- To flash the firmware, first put your board into bootloader mode by double clicking the reset button (either on the MCU board itself, or the one that is part of your keyboard).
- Copy the correct UF2 file (e.g. left or right if working on a split), and paste it onto the root of that USB mass storage device
- When the flash is complete, the controller should unmount the USB storage, automatically restart and load your newly flashed firmware
- After flashing each half individually you can connect them together by resetting them at the same time.

## Outro
*Once* your board works with the default firmware, you can modify the keymap.
Your copies of the default Hillside keymaps are in:
- [./config/hillside48.keymap](./config/hillside48.keymap)

Modify those as needed. Pushing the change will trigger a build as above.

If you want to enable features,
  modify the appropriate ./config/hillside*.conf file.

The Hillside shield definition files should *not* need to be modified and are in ./config/boards/shields.

More information about each keymap is in their readme files.
