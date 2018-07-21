# My fork of QMK to store my keyboard configurations
Look below for how to make a build environment.

To build my keyboards run

    make ergodox_ez:anders

or on Linux

    make ergodox_ez:anders:teensy

Start QMK ToolBox and check the Auto Flash checkbox. Open the firmware HEX-file called ergodox_ez_anders.hex which should be in qmk_firmware root directory

Press the RESET key on your keyboard (or a paperclip in the upper right hole on the keyboard) and the firmware should be immediately flashed to the keyboard. Then the keyboard will reboot and flash in the upper right corner.

    *** Halfkay device connected
    *** Attempting to flash, please don't remove device
    >>> teensy_loader_cli -mmcu=atmega32u4 /Users/megaman/qmk_firmware/ergodox_ez_anders.hex -v
        Teensy Loader, Command Line, Version 2.1
        Read "/Users/megaman/qmk_firmware/ergodox_ez_anders.hex": 25232 bytes, 78.2% usage
        Found HalfKay Bootloader

        Programming...............................................................................
        Booting

Do not close QMK Toolbox. All you need now to do is to change the configuration, make the project and then press the RESET key again. Wait for the lights on the keyboards upp right corner to flash. You do not need to bother QMK Toolbox again.

## Build environment
Make sure you have your [build environment setup](https://docs.qmk.fm/#/newbs_getting_started?id=environment-setup). Don't forget to install [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases/latest).

### Linux
When using Linux you will not be able to install QMK Toolbox. Instead you will use Teensy Loader CLI and be like a BAUSS! Do the following (instructions from https://www.pjrc.com/teensy/loader_cli.html and https://www.pjrc.com/teensy/loader_linux.html).

* Clone the source code:
  `git clone https://github.com/PaulStoffregen/teensy_loader_cli`
* Install libusb-dev
  `sudo apt install libusb-dev`
* Run make:
  `make`
* Export the PATH variable to  contain this directory (put this in the startup scripts)
* Don't forget to update the Udev rules:
  `curl -sSlo /tmp/49-teensy.rules https://www.pjrc.com/teensy/49-teensy.rules`
* Reconnect the keyboard (so Udev rules takes effect) and you are good to go.

## Branches
Instead of changing master, I will use my own branch for my changes. Consider master to be read only. This way I can keep the code up to date and rebase my branch on master. This separates my changes from theirs.

All my branches will be prefixed with "aquaplanet-", e.g. aquaplanet-master.

---

# Quantum Mechanical Keyboard Firmware

[![Current Version](https://img.shields.io/github/tag/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/tags)
[![Build Status](https://travis-ci.org/qmk/qmk_firmware.svg?branch=master)](https://travis-ci.org/qmk/qmk_firmware)
[![Discord](https://img.shields.io/discord/440868230475677696.svg)](https://discord.gg/Uq7gcHh)
[![Docs Status](https://img.shields.io/badge/docs-ready-orange.svg)](https://docs.qmk.fm)
[![GitHub contributors](https://img.shields.io/github/contributors/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/pulse/monthly)
[![GitHub forks](https://img.shields.io/github/forks/qmk/qmk_firmware.svg?style=social&label=Fork)](https://github.com/qmk/qmk_firmware/)

This is a keyboard firmware based on the [tmk\_keyboard firmware](http://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers, and more specifically, the [OLKB product line](https://olkb.com), the [ErgoDox EZ](http://www.ergodox-ez.com) keyboard, and the [Clueboard product line](http://clueboard.co/).

## Documentation

* [See the official documentation on docs.qmk.fm](https://docs.qmk.fm)

The docs are hosted on [Gitbook](https://www.gitbook.com/book/qmk/firmware/details) and [GitHub](/docs/) (they are synced). You can request changes by making a fork and [pull request](https://github.com/qmk/qmk_firmware/pulls), or by clicking the "suggest an edit" link on any page of the docs.

## Supported Keyboards

* [Planck](/keyboards/planck/)
* [Preonic](/keyboards/preonic/)
* [ErgoDox EZ](/keyboards/ergodox_ez/)
* [Clueboard](/keyboards/clueboard/)
* [Cluepad](/keyboards/clueboard/17/)

The project also includes community support for [lots of other keyboards](/keyboards/).

## Maintainers

QMK is developed and maintained by Jack Humbert of OLKB with contributions from the community, and of course, [Hasu](https://github.com/tmk). The OLKB product firmwares are maintained by [Jack Humbert](https://github.com/jackhumbert), the Ergodox EZ by [Erez Zukerman](https://github.com/ezuk), and the Clueboard by [Zach White](https://github.com/skullydazed).

## Official website

[http://qmk.fm](http://qmk.fm) is the official website of QMK, where you can find links to this page, the documentation, and the keyboards supported by QMK.
