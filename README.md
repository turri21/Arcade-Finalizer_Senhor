# Finalizer - Super Transformation for [MISTer](https://github.com/MiSTer-devel/Main_MiSTer/wiki)
An FPGA implementation of Finalizer - Super Transformation for the MiSTer platform

## Credits
- Sorgelig: MiSTer project lead
- Ace: Core design and Konami custom chip implementations
- ElectronAsh, Arnim Laeuger: Assistance with Konami custom chip implementations
- JimmyStones: High score saving support & pause feature
- Kitrinx: ROM loader

## Features
- Logic modelled to match the original as closely as possible
- Standard joystick and keyboard controls
- High score saving (Can be saved manually or automatically - manual saving is the default)
- Greg Miller's cycle-accurate MC6809E CPU core with modifications by Sorgelig and bugfixes by Arnim Laeuger and Jotego as the basis for the KONAMI-1 custom encrypted MC6809E
- SN76489 sound core by Arnim Laeuger with fixes by Ace and Enforcer
- T48 MCU by Arnim Laeuger configured as an NEC uPD8749 as the basis for the Konami SND01 custom chip
- Option for normalized video timings to use with picky HDTVs and monitors (underclocks the game by ~1.8%)

## Installation
Place `*.rbf` into the "_Arcade/cores" folder on your SD card.  Then, place `*.mra` into the "_Arcade" folder and ROM files from MAME into "games/mame".

### ****ATTENTION****
ROMs are not included. In order to use this arcade core, you must provide the correct ROMs.

To simplify the process, .mra files are provided in the releases folder that specify the required ROMs along with their checksums.  The ROM's .zip filename refers to the corresponding file in the M.A.M.E. project.

Please refer to https://github.com/MiSTer-devel/Main_MiSTer/wiki/Arcade-Roms for information on how to setup and use the environment.

Quick reference for folders and file placement:

/_Arcade/<game name>.mra
/_Arcade/cores/<game rbf>.rbf
/games/mame/<mame rom>.zip
/games/hbmame/<hbmame rom>.zip

## Controls
### Keyboard
| Key | Function |
| --- | --- |
| 1 | 1-Player Start |
| 2 | 2-Player Start |
| 5, 6 | Coin |
| 9 | Service Credit |
| Arrow keys | Movement |
| CTRL | Fire 1 |
| ALT | Fire 2/Shield |

### Joystick
| Joystick action | Function |
| --- | --- |
| D-Pad | Movement |
| B | Fire 1 |
| A | Fire 2/Shield |

## Known Issues
1) Although bootleg audio errors are recreated, the rest of the inaccurate behavior on bootleg Finalizer boards is currently unknown and not implemented

## High Score Save/Load
Save and load of high scores is supported for this core.

- To save your high scores manually, press the 'Save Settings' option in the OSD.  High scores will be automatically loaded when the core is started.
- To enable automatic saving of high scores, turn on the 'Autosave Hiscores' option, press the 'Save Settings' option in the OSD, and reload the core.  High scores will then be automatically saved (if they have changed) any time the OSD is opened.

High score data is stored in /media/fat/config/nvram/ as ```<mra filename>.nvm```
