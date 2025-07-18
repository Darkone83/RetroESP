<div align=center>
  <img src="https://github.com/Darkone83/RetroESP/blob/main/images/Logo.png" width=200 height=200> <img src="https://github.com/Darkone83/RetroESP/blob/main/images/DC%20logo.png">
</div>

# RetroESP: ESP32-Based Retro Game Console

RetroESP is a compact handheld retro game console powered by the ESP32. Inspired by classic handhelds, RetroESP brings NES, Gameboy, and other retro gaming experiences to a tiny, affordable platform. It features a pixel display, hardware buttons, and a simple user interface for browsing and launching games.

## Features

- Supports classic game emulators (NES, GameBoy, SMS, etc.)
- Menu-driven game launcher
- Save/load game states (where supported)
- Compact, handheld design
- SD card support for ROMs and BIOS files
- Open-source firmware, based on [retro-go](https://github.com/ducalex/retro-go) and adapted for ST7789 displays

## Hardware Overview

- **Microcontroller:** ESP32 WROOM E Devkit C V4
- **Display:** 2.4 inch ST7789 SPI TFT LCD
- **Controls:** Tactile buttons for D-Pad and A/B/Start/Select
- **Storage:** microSD card for game ROMs, BIOS, and save files
- **Power:** LiPo battery or USB
- **Audio:** Built-in speaker or headphones

## Usage

### 1. Preparing the SD Card

- **ROMs:**  
  Place your legally owned ROMs in the `/roms` directory on the SD card.  
  Supported folders:  
    - `/roms/gb/` (GameBoy)
    - `/roms/nes/` (NES)
    - `/roms/sms/` (Sega Master System)
    - `/roms/gg/` (Game Gear)
    - **etc**

- **BIOS Files:**  
  Some emulators require BIOS files. Place them in `/bios/` on the SD card.  
  Example:
    - `/bios/gb_bios.bin` (GameBoy)
    - `/bios/gbc_bios.bin` (GameBoy Color)
    - `/bios/fds_bios.bin` (Famicom Disk System)

- **Launcher Images:**  
  You can add `.png` images in `/launcher/images` to display custom thumbnails in the launcher menu.

### 2. Flashing the Firmware

- Use [ESP32 Arduino](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html) or [PlatformIO](https://platformio.org/) to compile and flash the firmware to your ESP32.
- Make sure to select the correct board and set the flash mode to QIO/DIO if using a WROVER module.
- Connect your ESP32 to your PC via USB and upload as usual.

### 3. Usage & Controls

- Insert the microSD card and power on the device.
- Browse the launcher using the D-Pad.
- Press **A** to launch a game.
- In-game, use **Start/Select** as needed.
- To exit a game and return to the launcher, press and hold **Select + Start** (or as configured in your build).

### 4. Save & Load States

- Most emulators support save and load states.  
  Refer to in-game menus or the help section for button combinations.

### 5. Supported Emulators

- NES (Nintendo Entertainment System)
- GB/GBC (Game Boy / Color)
- SMS (Sega Master System)
- GG (Game Gear)
- Others as available in your build

## Acknowledgements

- The design of the launcher was inspired (copied) from <a href="https://github.com/pelle7/odroid-go-emu-launcher">pelle7's **go-emu**.</a>
- The NES/GBC/SMS emulators and base library were originally from the "Triforce" fork of the <a href="https://github.com/othercrashoverride/go-play">official Go-Play firmware</a> by **crashoverride**, **Nemo1984**, and many others.
- **PCE-GO** is a fork of <a href="https://github.com/kallisti5/huexpress">**HuExpress**</a> and <a href="https://github.com/pelle7/odroid-go-pcengine-huexpress/">pelle7's port</a> was used as reference.
- The Lynx emulator is a port of <a href="https://github.com/libretro/libretro-handy">**libretro-handy**.</a>
- The SNES emulator is a port of <a href="https://github.com/libretro/snes9x2005">**Snes9x 2005**.</a>
- The DOOM engine is a port of <a href="https://prboom.sourceforge.net/">**PrBoom 2.5.0**.</a>
- The Genesis emulator is a port of <a href="https://github.com/bzhxx/gwenesis/">**Gwenenesis**</a> by **bzhxx**.
- The Game & Watch emulator is a port of <a href="https://github.com/bzhxx/lcd-game-emulator">**lcd-game-emulator**</a> by **bzhxx**.
- PNG support is provided by <a href="https://github.com/lvandeve/lodepng/">**lodepng**.</a>
- PCE cover art is from <a href="https://github.com/christianhaitian">**Christian_Haitian**.</a>
- Some icons from <a href="https://iconarchive.com/show/seed-icons-by-rokey.html">**Rokey**.</a>
- Background images from <a href="https://github.com/rxbrad/es-theme-gbz35">**es-theme-gbz35**.</a>
- The <a href="https://forum.odroid.com/viewtopic.php?f=159&t=37599">**ODROID-GO**</a> community for encouraging the development of retro-go!
- [@ducalex / retro-go](https://github.com/ducalex/retro-go) - the core project and firmware for ESP32-based retro game consoles  
- [@geebles](https://github.com/geebles/retro-go) - for S3 support and numerous code enhancements  
- [@beaups](https://github.com/beaups/retro-go) - for his continued contributions and hardware compatibility fixes  
- [@timoinutilis](https://github.com/timoinutilis/retro-go) - for work on the TTGO VGA32 variant  
- [jobitjoseph/retro-go-ST7789](https://github.com/jobitjoseph/retro-go-ST7789) - for the ST7789 display adaptation and launcher improvements  
- [CircuitDigest](https://circuitdigest.com/microcontroller-projects/esp32-based-retro-game-console) - for the original hardware inspiration and guide  

Special thanks to all contributors and maintainers of these and related open-source projects.

## Legal

- Only use ROMs and BIOS files that you own the rights to.
- This project is for educational and personal use only.

---

<div align=center>
  <img src="https://github.com/Darkone83/RetroESP/blob/main/images/logo2.png" height=200 width=200> <img src="https://github.com/Darkone83/RetroESP/blob/main/images/Victory.png" width=200 height=200">
</div>

**Enjoy retro gaming on your ESP32!**

---

## License

Everything in this project is licensed under the <a href="https://github.com/jobitjoseph/retro-go-ST7789/blob/master/COPYING">GPLv2 license</a> with the exception of the following components:

- components/retro-go (Retro-Go's framework, zlib)
- handy-go/components/handy (Lynx emulator, zlib)
