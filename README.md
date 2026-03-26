<p align="center"><img src="buildroot/share/pixmaps/logo/marlin-outrun-nf-500.png" height="250" alt="MarlinFirmware's logo" /></p>

<h1 align="center">Marlin 3D Printer Firmware</h1>

<p align="center">
    <a href="/LICENSE"><img alt="GPL-V3.0 License" src="https://img.shields.io/github/license/marlinfirmware/marlin.svg"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/marlinfirmware/marlin.svg"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/releases"><img alt="Last Release Date" src="https://img.shields.io/github/release-date/MarlinFirmware/Marlin"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/actions/workflows/ci-build-tests.yml"><img alt="CI Status" src="https://github.com/MarlinFirmware/Marlin/actions/workflows/ci-build-tests.yml/badge.svg"></a>
    <a href="https://github.com/sponsors/thinkyhead"><img alt="GitHub Sponsors" src="https://img.shields.io/github/sponsors/thinkyhead?color=db61a2"></a>
    <br />
    <a href="https://fosstodon.org/@marlinfirmware"><img alt="Follow MarlinFirmware on Mastodon" src="https://img.shields.io/mastodon/follow/109450200866020466?domain=https%3A%2F%2Ffosstodon.org&logoColor=%2300B&style=social"></a>
</p>

Additional documentation can be found at the [Marlin Home Page](//marlinfw.org/).
Please test this firmware and let us know if it misbehaves in any way. Volunteers are standing by!

## Marlin 2.1

Marlin 2.1 continues to support both 32-bit ARM and 8-bit AVR boards while adding support for up to 9 coordinated axes and to up to 8 extruders.

Download earlier versions of Marlin on the [Releases page](//github.com/MarlinFirmware/Marlin/releases).

## Example Configurations

Before you can build Marlin for your machine you'll need a configuration for your specific hardware. Upon request, your vendor will be happy to provide you with the complete source code and configurations for your machine, but you'll need to get updated configuration files if you want to install a newer version of Marlin. Fortunately, Marlin users have contributed dozens of tested configurations to get you started. Visit the [MarlinFirmware/Configurations](//github.com/MarlinFirmware/Configurations) repository to find the right configuration for your hardware.

## Building Marlin 2.1

To build and upload Marlin you will use one of these tools:

- The free [Visual Studio Code](//code.visualstudio.com/download) using the [Auto Build Marlin](//marlinfw.org/docs/basics/auto_build_marlin.html) extension.
- The free [Arduino IDE](//www.arduino.cc/en/main/software) : See [Building Marlin with Arduino](//marlinfw.org/docs/basics/install_arduino.html)
- You can also use VSCode with devcontainer : See [Installing Marlin (VSCode devcontainer)](http://marlinfw.org/docs/basics/install_devcontainer_vscode.html).

Marlin is optimized to build with the **PlatformIO IDE** extension for **Visual Studio Code**. You can still build Marlin with **Arduino IDE**, and we hope to improve the Arduino build experience, but at this time PlatformIO is the better choice.

## 8-Bit AVR Boards

We intend to continue supporting 8-bit AVR boards in perpetuity, maintaining a single codebase that can apply to all machines. We want casual hobbyists and tinkerers and owners of older machines to benefit from the community's innovations just as much as those with fancier machines. Plus, those old AVR-based machines are often the best for your testing and feedback!

## Hardware Abstraction Layer (HAL)

Marlin includes an abstraction layer to provide a common API for all the platforms it targets. This allows Marlin code to address the details of motion and user interface tasks at the lowest and highest levels with no system overhead, tying all events directly to the hardware clock.

Every new HAL opens up a world of hardware. At this time we need HALs for RP2040 and the Duet3D family of boards. A HAL that wraps an RTOS is an interesting concept that could be explored. Did you know that Marlin includes a Simulator that can run on Windows, macOS, and Linux? Join the Discord to help move these sub-projects forward!

### Supported Platforms

  Platform|MCU|Example Boards
  --------|---|-------
  [Arduino AVR](//www.arduino.cc/)|ATmega|RAMPS, Melzi, RAMBo
  [Teensy++ 2.0](//www.microchip.com/en-us/product/AT90USB1286)|AT90USB1286|Printrboard
  [Arduino Due](//www.arduino.cc/en/Guide/ArduinoDue)|SAM3X8E|RAMPS-FD, RADDS, RAMPS4DUE
  [ESP32](//github.com/espressif/arduino-esp32)|ESP32|FYSETC E4, E4d@BOX, MRR
  [LPC1768](//www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/general-purpose-mcus/lpc1700-cortex-m3/512-kb-flash-64-kb-sram-ethernet-usb-lqfp100-package:LPC1768FBD100)|ARM® Cortex-M3|MKS SBASE, Re-ARM, Selena Compact
  [LPC1769](//www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/general-purpose-mcus/lpc1700-cortex-m3/512-kb-flash-64-kb-sram-ethernet-usb-lqfp100-package:LPC1769FBD100)|ARM® Cortex-M3|Smoothieboard, Azteeg X5 mini, TH3D EZBoard
  [STM32F103](//www.st.com/en/microcontrollers-microprocessors/stm32f103.html)|ARM® Cortex-M3|Malyan M200, GTM32 Pro, MKS Robin, BTT SKR Mini
  [STM32F401](//www.st.com/en/microcontrollers-microprocessors/stm32f401.html)|ARM® Cortex-M4|ARMED, Rumba32, SKR Pro, Lerdge, FYSETC S6, Artillery Ruby
  [STM32F7x6](//www.st.com/en/microcontrollers-microprocessors/stm32f7x6.html)|ARM® Cortex-M7|The Borg, RemRam V1
  [STM32G0B1RET6](//www.st.com/en/microcontrollers-microprocessors/stm32g0x1.html)|ARM® Cortex-M0+|BigTreeTech SKR mini E3 V3.0
  [STM32H743xIT6](//www.st.com/en/microcontrollers-microprocessors/stm32h743-753.html)|ARM® Cortex-M7|BigTreeTech SKR V3.0, SKR EZ V3.0, SKR SE BX V2.0/V3.0
  [SAMD21P20A](//www.adafruit.com/product/4064)|ARM® Cortex-M0+|Adafruit Grand Central M4
  [SAMD51P20A](//www.adafruit.com/product/4064)|ARM® Cortex-M4|Adafruit Grand Central M4
  [Teensy 3.2/3.1](//www.pjrc.com/teensy/teensy31.html)|MK20DX256VLH7 ARM® Cortex-M4|
  [Teensy 3.5](//www.pjrc.com/store/teensy35.html)|MK64FX512-VMD12 ARM® Cortex-M4|
  [Teensy 3.6](//www.pjrc.com/store/teensy36.html)|MK66FX1MB-VMD18 ARM® Cortex-M4|
  [Teensy 4.0](//www.pjrc.com/store/teensy40.html)|MIMXRT1062-DVL6B ARM® Cortex-M7|
  [Teensy 4.1](//www.pjrc.com/store/teensy41.html)|MIMXRT1062-DVJ6B ARM® Cortex-M7|
  Linux Native|x86 / ARM / RISC-V|Raspberry Pi GPIO
  Simulator|Windows, macOS, Linux|Desktop OS
  [All supported boards](//marlinfw.org/docs/hardware/boards.html#boards-list)|All platforms|All boards

## Marlin Support

The Issue Queue is reserved for Bug Reports and Feature Requests. Please use the following resources for help with configuration and troubleshooting:

- [Marlin Documentation](//marlinfw.org) - Official Marlin documentation
- [Marlin Discord](//discord.com/servers/marlin-firmware-461605380783472640) - Discuss issues with Marlin users and developers
- Facebook Group ["Marlin Firmware"](//www.facebook.com/groups/1049718498464482/)
- RepRap.org [Marlin Forum](//forums.reprap.org/list.php?415)
- Facebook Group ["Marlin Firmware for 3D Printers"](//www.facebook.com/groups/3Dtechtalk/)
- [Marlin Configuration](//www.youtube.com/results?search_query=marlin+configuration) on YouTube

## Contributing Patches

You can contribute patches by submitting a Pull Request to the ([bugfix-2.1.x](//github.com/MarlinFirmware/Marlin/tree/bugfix-2.1.x)) branch.

- We use branches named with a "bugfix" or "dev" prefix to fix bugs and integrate new features.
- Follow the [Coding Standards](//marlinfw.org/docs/development/coding_standards.html) to gain points with the maintainers.
- Please submit Feature Requests and Bug Reports to the [Issue Queue](//github.com/MarlinFirmware/Marlin/issues/new/choose). See above for user support.
- Whenever you add new features, be sure to add one or more build tests to `buildroot/tests`. Any tests added to a PR will be run within that PR on GitHub servers as soon as they are pushed. To minimize iteration be sure to run your new tests locally, if possible.
  - Local build tests:
    - All: `make tests-config-all-local`
    - Single: `make tests-config-single-local TEST_TARGET=...`
  - Local build tests in Docker:
    - All: `make tests-config-all-local-docker`
    - Single: `make tests-config-all-local-docker TEST_TARGET=...`
  - To run all unit test suites:
    - Using PIO: `platformio run -t test-marlin`
    - Using Make: `make unit-test-all-local`
    - Using Docker + make: `maker unit-test-all-local-docker`
  - To run a single unit test suite:
    - Using PIO: `platformio run -t marlin_<test-suite-name>`
    - Using make: `make unit-test-single-local TEST_TARGET=<test-suite-name>`
    - Using Docker + make: `maker unit-test-single-local-docker TEST_TARGET=<test-suite-name>`
- If your feature can be unit tested, add one or more unit tests. For more information see our documentation on [Unit Tests](test).

## Contributors

Marlin is constantly improving thanks to a huge number of contributors from all over the world bringing their specialties and talents. Huge thanks are due to [all the contributors](//github.com/MarlinFirmware/Marlin/graphs/contributors) who regularly patch up bugs, help direct traffic, and basically keep Marlin from falling apart. Marlin's continued existence would not be possible without them.

Marlin Firmware original logo design by Ahmet Cem TURAN [@ahmetcemturan](//github.com/ahmetcemturan).

## Project Leadership

Name|Role|Link|Donate
----|----|----|----
🇺🇸 Scott Lahteine|Project Lead|[[@thinkyhead](//github.com/thinkyhead)]|[💸 Donate](//marlinfw.org/docs/development/contributing.html#donate)
🇺🇸 Roxanne Neufeld|Admin|[[@Roxy-3D](//github.com/Roxy-3D)]|
🇺🇸 Keith Bennett|Admin|[[@thisiskeithb](//github.com/thisiskeithb)]|[💸 Donate](//github.com/sponsors/thisiskeithb)
🇺🇸 Jason Smith|Admin|[[@sjasonsmith](//github.com/sjasonsmith)]|
🇧🇷 Victor Oliveira|Admin|[[@rhapsodyv](//github.com/rhapsodyv)]|
🇬🇧 Chris Pepper|Admin|[[@p3p](//github.com/p3p)]|
🇳🇿 Peter Ellens|Admin|[[@ellensp](//github.com/ellensp)]|[💸 Donate](//ko-fi.com/ellensp)
🇺🇸 Bob Kuhn|Admin|[[@Bob-the-Kuhn](//github.com/Bob-the-Kuhn)]|
🇳🇱 Erik van der Zalm|Founder|[[@ErikZalm](//github.com/ErikZalm)]|

## Star History

<a id="starchart" href="https://star-history.com/#MarlinFirmware/Marlin&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=MarlinFirmware/Marlin&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=MarlinFirmware/Marlin&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=MarlinFirmware/Marlin&type=Date" />
  </picture>
</a>

## Ender-5 / SKR Mini E3 V3.0 Configuration (`skr_mini_e3_v3.0` branch)

This branch contains a customised configuration for a **Creality Ender-5** running on a **BigTreeTech SKR Mini E3 V3.0** board with onboard TMC2209 drivers. It was adapted from the `main` branch, which targeted the SKR 1.4 Turbo (LPC1769). The sections below document every change made to the stock Marlin files.

### `platformio.ini`

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `default_envs` | `mega2560` | `STM32G0B1RE_btt` | The SKR Mini E3 V3.0 uses an STM32G0B1RET6 MCU (STM32G0 family). This selects the correct build toolchain and upload offset. |

---

### `Marlin/Configuration.h`

#### Top-level custom macros (added)

A set of macros at the top of the file acts as a single place to toggle hardware options. All conditional blocks throughout the file key off these.

| Macro | Default | Description |
|---|---|---|
| `E3D` | disabled | Enable for an E3D all-metal hotend — changes thermistor type to ATC Semitec 104GT-2 (type 5) and caps max temp at 300 °C. |
| `E3D_Extreme` | **enabled** | Enable to allow printing above 285 °C (max temp 320 °C). Also selects the ATC Semitec 104GT-2 thermistor (type 5), which is required for the higher temperature range. Use with caution; E3D advises against sustained use above 285 °C. |
| `chamber` | disabled | Enable for a heated chamber. Activates `TEMP_SENSOR_CHAMBER` on TEMP-E1 and the heater on the spare port. |
| `TMC2209_Enabled` | **enabled** | Switches all four driver types to `TMC2209`. Disable to fall back to generic `A4988` pinout. |
| `SKR_MINI_E3_V3_0` | **enabled** | Selects the `BOARD_BTT_SKR_MINI_E3_V3_0` motherboard definition. Disable to fall back to `BOARD_MELZI_CREALITY`. |

#### Board and identity

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `CONFIG_EXAMPLES_DIR` | *(absent)* | `"Creality/Ender-5/BigTreeTech SKR Mini E3 V3.0 (TMC2209)"` | Documents the origin of this configuration. |
| `MOTHERBOARD` | `BOARD_RAMPS_14_EFB` | `BOARD_BTT_SKR_MINI_E3_V3_0` (via `SKR_MINI_E3_V3_0` macro) | Selects the correct pin map for the SKR Mini E3 V3.0. |
| `STRING_CONFIG_H_AUTHOR` | `(none, default config)` | `(mribeiro, Ender-5)` | Identifies the build author in `M115` output. |

#### Boot screen

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `SHOW_CUSTOM_BOOTSCREEN` | disabled | disabled | Requires `Marlin/_Bootscreen.h` to exist; left disabled until a custom bitmap is added. |
| `CUSTOM_STATUS_SCREEN_IMAGE` | disabled | disabled | Requires `Marlin/_Statusscreen.h` to exist; left disabled until a custom bitmap is added. |

#### Serial / USB communication

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `SERIAL_PORT` | `0` | `-1` | Port `-1` is the USB-emulated serial port on the SKR Mini E3 V3.0, matching the behaviour of the SKR 1.4 Turbo. |
| `SERIAL_PORT_2` | disabled | disabled | STM32G0 does not accept port `0`; valid values are 1–9 or `-1`. Since a TFT display is not in use, this port is left disabled. Enable with value `1` if an OctoPrint adapter or TFT is later connected to the UART1 header. |
| `BAUDRATE` | `250000` | `115200` | Matches the baud rate used by the previous SKR 1.4 Turbo configuration. |

#### Stepper drivers

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `X/Y/Z/E0_DRIVER_TYPE` | `A4988` | `TMC2209` (when `TMC2209_Enabled`) | The SKR Mini E3 V3.0 has onboard TMC2209 drivers. Using the correct driver type enables UART control, StealthChop, and CoolStep. |

#### Temperature sensors

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `TEMP_SENSOR_0` | `1` (100 k EPCOS) | `5` when `E3D` or `E3D_Extreme`, else `1` | The E3D hotend uses an ATC Semitec 104GT-2 thermistor (type 5). This type is mandatory when `E3D_Extreme` is active: the standard type-1 table only reaches ~300 °C, so pairing it with MAXTEMP=320 is a compile error. |
| `TEMP_SENSOR_CHAMBER` | `0` | `1` when `chamber`, else `0` | Enables chamber temperature sensing on the spare TEMP-E1 port when the `chamber` macro is active. |
| `HEATER_0_MAXTEMP` | `275` | `300` (`E3D`) / `320` (`E3D_Extreme`) / `275` (default) | Raises the safety cutoff to match the hotend capability. The `E3D_Extreme` limit should only be used for brief, supervised operations. |
| `BED_MAXTEMP` | `150` | `125` | The Ender-5 stock bed is only rated to ~110 °C; 125 °C provides headroom while avoiding false MAXTEMP trips. |

#### Motion — steps per mm

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `DEFAULT_AXIS_STEPS_PER_UNIT` | `{ 80, 80, 400, 500 }` | `{ 79.50, 79.80, 800, 93 }` | Calibrated values for this specific Ender-5 frame (GT2 belts/pulleys, 400-step/rev Z lead-screw, direct-drive extruder). |

#### Motion — speed and acceleration

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `DEFAULT_MAX_FEEDRATE` | `{ 300, 300, 5, 25 }` | `{ 500, 500, 10, 50 }` | Conservative limits tuned for the Ender-5 CoreXY-style moving-bed geometry. |
| `DEFAULT_MAX_ACCELERATION` | `{ 3000, 3000, 100, 10000 }` | `{ 500, 500, 100, 5000 }` | Lower X/Y acceleration reduces ringing on the Ender-5 moving-bed. |
| `DEFAULT_ACCELERATION` | `3000` | `500` | Print-move acceleration matched to the Ender-5 frame rigidity. |
| `DEFAULT_RETRACT_ACCELERATION` | `3000` | `1000` | Gentler retraction acceleration to protect the direct-drive extruder. |
| `DEFAULT_TRAVEL_ACCELERATION` | `3000` | `500` | Travel (non-print) acceleration aligned with print acceleration. The stock 3000 mm/s² was inconsistent with the 500 mm/s² print value and would cause the frame to vibrate during fast travel moves. |

#### Stepper direction

The Ender-5 uses a **mirrored X coordinate system**: the X endstop is on the physical right side, so X=0 is at the right and X increases going left. This means `INVERT_X_DIR false` correctly homes the carriage rightward (toward the endstop) on negative steps. Y is similar — the endstop is at the rear, Y=0 is rear, Y increases toward the front.

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `INVERT_X_DIR` | `false` | `false` | With the mirrored X coordinate, negative steps naturally move the carriage right toward the endstop. No inversion needed. |
| `INVERT_Y_DIR` | `false` | `false` | Same reasoning as X. Negative steps move the bed toward the rear endstop. |
| `INVERT_Z_DIR` | `false` | `true` | Motor wiring requires inversion so that positive Z steps raise the bed (increase nozzle-to-bed distance). |
| `INVERT_E0_DIR` | `false` | `true` | Motor wiring requires inversion for correct filament feed direction. |

#### Endstop configuration

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `USE_XMIN_PLUG` | enabled | enabled | X endstop is wired to the X-STOP (X_MIN) connector. |
| `USE_YMIN_PLUG` | enabled | enabled | Y endstop is wired to the Y-STOP (Y_MIN) connector. |
| `USE_ZMIN_PLUG` | enabled | enabled | The inductive probe is wired to the Z-STOP (Z_MIN) connector. |
| `X_HOME_DIR` | `-1` | `-1` | Home to X_MIN (physical right side). |
| `Y_HOME_DIR` | `-1` | `-1` | Home to Y_MIN (physical rear). |
| `Z_HOME_DIR` | `-1` | `-1` | Home downward (probe triggers before nozzle reaches bed). |
| `Z_MIN_ENDSTOP_INVERTING` | `false` | `true` | The inductive probe interface board inverts the output signal. `true` corrects this so M119 shows OPEN when away from metal and TRIGGERED when near. |
| `Z_MIN_PROBE_ENDSTOP_INVERTING` | `false` | `true` | Must match `Z_MIN_ENDSTOP_INVERTING` since both use the same Z-STOP pin. |

#### Probe type and offset

The probe is an **inductive sensor** mounted to the left of the hotend carriage (when viewed from the front of the printer).

**Coordinate system note:** On the Ender-5, positive X = physically left (because the X endstop is on the right and X=0 is at the endstop). Therefore a probe that is to the **left** of the nozzle has a **positive X offset**.

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `FIX_MOUNTED_PROBE` | disabled | **enabled** | Declares a probe permanently fixed to the carriage (no deploy/stow). Required for `AUTO_BED_LEVELING_BILINEAR`. |
| `NOZZLE_TO_PROBE_OFFSET` | `{ 10, 10, 0 }` | `{ 46, 9, 0 }` | Probe is ~46 mm to the LEFT (+X) and ~9 mm toward the front (+Y) of the nozzle. Z component is a placeholder — calibrate with `M851` after first boot. |
| `Z_PROBE_LOW_POINT` | `-2` | `-5` | Allows 5 mm of descent past the expected trigger point. Gives sufficient range for inductive probes mounted slightly above optimal height without risking a hard crash. |

#### Bed geometry

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `X_BED_SIZE` | `200` | `216` | Physical X travel is limited to 216 mm — commanding X > 216 crashes the carriage into the left frame. `X_BED_SIZE` must equal `X_MAX_POS` to satisfy Marlin's sanity check. |
| `Y_BED_SIZE` | `200` | `220` | The Ender-5 Y axis has the full 220 mm of travel. |
| `X_MAX_POS` | `X_BED_SIZE` | `216` | Soft endstop — Marlin refuses to move the nozzle beyond this value. |
| `Z_MAX_POS` | `200` | `300` | The Ender-5 Z travel is 300 mm. |

#### Auto Bed Leveling

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `AUTO_BED_LEVELING_BILINEAR` | disabled | **enabled** | Enables bilinear mesh leveling with the fixed probe. |
| `GRID_MAX_POINTS_X` | `3` | `5` | 5 × 5 = 25-point mesh for better leveling accuracy. |
| `MULTIPLE_PROBING` | disabled | `2` | Probes each mesh point twice and averages the results, reducing the effect of electrical noise on the mesh. |
| `PROBING_MARGIN` | `10` | `10` | Default 10 mm margin from all bed edges. Overridden on the left side by `PROBING_MARGIN_RIGHT`. |
| `PROBING_MARGIN_RIGHT` | *(not set)* | `46` | Limits how close the probe gets to `X_MAX_BED` (the physical left side). With probe offset X=+46, the default margin would allow the probe to reach X=210 — too close to the left frame. Setting this to 46 limits probe maximum X to 174 mm, keeping the nozzle at ≤ 128 mm. |
| `Z_SAFE_HOMING` | disabled | **enabled** | Moves XY to the probe position before homing Z, preventing the nozzle from contacting the bed at an unprobed corner. |

#### Display

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `DISPLAY_CHARSET_HD44780` | `JAPANESE` | `WESTERN` | Displays Latin characters correctly on the CR-10 stock display. |
| `CR10_STOCKDISPLAY` | disabled | **enabled** | The Ender-5 uses the CR-10 stock display (EXP1 connector). |
| `ENCODER_PULSES_PER_STEP` | disabled | `4` | The CR-10 stock rotary encoder generates 4 pulses per detent. Without this, each menu item requires turning the knob 4 steps instead of 1. |
| `ENCODER_STEPS_PER_MENU_ITEM` | disabled | `1` | Pairs with `ENCODER_PULSES_PER_STEP` so one physical click advances exactly one menu item. |
| `EEPROM_SETTINGS` | disabled | **enabled** | Allows saving configuration to flash with `M500`. Without this, the ABL mesh, Z offset, PID values and all runtime settings revert to firmware defaults on every power cycle. |
| `SDSUPPORT` | disabled | **enabled** | Enables the SD card slot on the SKR Mini E3 V3.0. Without it the printer can only receive jobs over USB. |

---

### `Marlin/Configuration_adv.h`

#### Header

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `CONFIG_EXAMPLES_DIR` | *(absent)* | `"Creality/Ender-5/BigTreeTech SKR Mini E3 V3.0 (TMC2209)"` | Keeps the origin label consistent with `Configuration.h`. |

#### TMC driver currents

Lower current reduces heat and noise without sacrificing torque at Ender-5 print speeds.

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `X_CURRENT` | `800 mA` | `650 mA` | Sufficient for Ender-5 X axis mass at typical speeds. |
| `Y_CURRENT` | `800 mA` | `650 mA` | Sufficient for Ender-5 Y axis (moving bed). |
| `Z_CURRENT` | `800 mA` | `580 mA` | The single Z motor on the Ender-5 needs less current; lower value reduces heat. |
| `E0_CURRENT` | `800 mA` | `650 mA` | Adequate for the direct-drive extruder. |

#### TMC UART addressing

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `X_SLAVE_ADDRESS` | commented out | `0` | All four drivers share a single UART bus (MSerial4). The board's pins file hard-asserts these exact values; any mismatch is a compile error. |
| `Y_SLAVE_ADDRESS` | commented out | `2` | See above. |
| `Z_SLAVE_ADDRESS` | commented out | `1` | See above. |
| `E0_SLAVE_ADDRESS` | commented out | `3` | See above. |

#### TMC chopper and modes

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `CHOPPER_TIMING` | `CHOPPER_DEFAULT_12V` | `CHOPPER_DEFAULT_24V` | The SKR Mini E3 V3.0 runs on a 24 V supply; the 24 V chopper preset gives optimal performance. |
| `HYBRID_THRESHOLD` | disabled | **enabled** | Automatically switches from silent StealthChop to spreadCycle above the configured speed threshold (X/Y: 100 mm/s, Z: 3 mm/s, E: 30 mm/s). |
| `TMC_DEBUG` | disabled | **enabled** | Enables `M122` to report live driver parameters — useful for diagnostics. |
| `DIAG_JUMPERS_REMOVED` | undefined | **defined** | Suppresses the build warning for boards with DIAG pins routed to endstop headers. The SKR Mini E3 V3.0 uses removable jumpers for DIAG; with physical endstops in use, those jumpers must be removed. |

#### Hotend heatsink fan

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `E0_AUTO_FAN_PIN` | `-1` (disabled) | `FAN1_PIN` | Assigns the hotend heatsink fan to the FAN1 header (PC7). The fan turns on automatically when the hotend exceeds `EXTRUDER_AUTO_FAN_TEMPERATURE` (50 °C) and off when it cools below. |

#### Probing and first-layer adjustment

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `BABYSTEPPING` | disabled | **enabled** | Allows adjusting the Z offset in real time while printing via the LCD menu. |
| `BABYSTEP_ZPROBE_OFFSET` | disabled | **enabled** | Links babystepping to the `M851` Z probe offset so adjustments persist after `M500`. |

---

## Optional Features (not enabled)

The following settings were reviewed but left at their stock (disabled) values. Enable them when you are ready to go through the corresponding setup steps.

### `Marlin/Configuration.h`

#### Bed temperature control

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `PIDTEMPBED` | Uncomment `#define PIDTEMPBED` | Switches the heated bed from bang-bang to closed-loop PID control, giving tighter temperature stability. | Run `M303 E-1 C8 S60` (autotune at 60 °C for 8 cycles), then `M500`. |

#### Motion quality

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `S_CURVE_ACCELERATION` | Uncomment `#define S_CURVE_ACCELERATION` | Replaces trapezoidal velocity profile with a smooth S-curve, reducing ringing without reducing speed. | None — enable and test. |

### `Marlin/Configuration_adv.h`

#### Extrusion quality

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `LIN_ADVANCE` | Uncomment `#define LIN_ADVANCE`, set `LIN_ADVANCE_K 0` | Compensates for nozzle pressure build-up, reducing blobs at corners. | Per-filament K-factor calibration required. |

#### Resilience

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `POWER_LOSS_RECOVERY` | Uncomment `#define POWER_LOSS_RECOVERY` | Saves print state to SD card so a print can resume after a power cut. | Verify the Z lead screw does not back-drive under gravity when power is cut. |
| `FILAMENT_RUNOUT_SENSOR` | Uncomment `#define FILAMENT_RUNOUT_SENSOR` | Pauses the print when filament runs out. | Requires a sensor wired to the `E0-STOP` header and `ADVANCED_PAUSE_FEATURE`. |
| `ADVANCED_PAUSE_FEATURE` | Uncomment `#define ADVANCED_PAUSE_FEATURE` | Enables guided filament-change (`M600`) and park-on-pause. | Requires `NOZZLE_PARK_FEATURE`. Configure load/unload lengths for your extruder path. |

#### Resonance compensation

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `INPUT_SHAPING_X` / `INPUT_SHAPING_Y` | Uncomment both in `Configuration_adv.h` | Notch filter cancels the printer's resonant frequency, greatly reducing ringing at higher speeds. Supported on the STM32G0B1. | Measure resonant frequency per axis (print ringing test tower or use ADXL345 + `M593`). Set `SHAPING_FREQ_X/Y` before enabling. |

---

## Calibration Reference

### Steps per mm

#### X and Y axes — GT2 belt / 20-tooth pulley / TMC2209

```
Steps/mm = (200 × 16) / (20 × 2 mm) = 80.000 steps/mm  (theoretical)
Firmware: X=79.50, Y=79.80  (±0.6% — within normal belt/pulley variation)
```

Re-verify with a calliper: command `G0 X100`, measure actual travel, compute `current_steps × 100 / actual_mm`. Save with `M92 X<value> Y<value>` then `M500`.

#### Z axis — TR8×4 lead screw (4 mm lead)

```
Steps/mm = (200 × 16) / 4 mm = 800.000 steps/mm  (mathematically exact)
```

No re-verification needed unless the lead screw is replaced.

#### E axis — direct drive MK8 gear

Firmware uses `93 steps/mm` (effective drive diameter ≈ 10.95 mm, consistent with Creality MK8). Verify before printing:

1. Mark filament 100 mm and 120 mm from extruder entry.
2. `G1 E100 F100` (cold, tension released).
3. New steps = `93 × 100 / actual_mm`. Save with `M92 E<value>` then `M500`.

---

### Probe offsets

#### Coordinate system

The Ender-5 X axis is **mirrored**: the endstop is on the physical right side, so X=0 is at the right and positive X moves the carriage left. As a result:

- A probe to the **physical left** of the nozzle has a **positive X offset** in firmware.
- A probe to the **physical front** of the nozzle has a **positive Y offset** in firmware (Y=0 is at the rear endstop).

#### X offset: +46 mm

```
Probe min X reachable: X_MIN_POS + offset.x = 0 + 46 = 46 mm  (nozzle at X=0)
Probe max X reachable: limited by PROBING_MARGIN_RIGHT=46 → X_MAX_BED − 46 = 216 − 46 = 170 mm
                       (nozzle at 170 − 46 = 124 mm)

Probed X range: [46 → 170] = 124 mm
Unprobed right strip: ~46 mm (probe physically cannot reach the right side of the bed
                      without the nozzle going past the right soft endstop)
```

#### Y offset: +9 mm

```
Probe min Y: Y_MIN_BED + PROBING_MARGIN + offset.y = 0 + 10 + 9 = 19 mm  (nozzle at 10 mm)
Probe max Y: Y_MAX_BED − PROBING_MARGIN + offset.y = 220 − 10 + 9 = 219 mm → clamped to 220

Probed Y range: [19 → 210] = ~191 mm
```

#### Z offset: 0 (placeholder)

The Z component of `NOZZLE_TO_PROBE_OFFSET` is `0` and must be calibrated on the physical printer. Procedure:

1. `M851 Z0` — clear any stored offset.
2. `G28` — home all axes.
3. Use `BABYSTEP_ZPROBE_OFFSET` (LCD → Tune → Z Offset) while printing a first-layer skirt to dial in the height until a sheet of paper drags with light resistance under the nozzle.
4. `M500` — save.

---

### Motor directions

| Axis | `INVERT_*_DIR` | Rationale |
|------|---------------|-----------|
| X | `false` | Mirrored coordinate (X=0 at right endstop): negative steps naturally move the carriage right toward the endstop. No inversion needed. |
| Y | `false` | Same reasoning: Y=0 at rear endstop, negative steps move the bed rearward toward the endstop. |
| Z | `true` | Motor wiring requires inversion so that positive Z steps raise the bed (increase nozzle-to-bed clearance). |
| E0 | `true` | Motor wiring requires inversion for correct filament feed direction. |

Verify on first boot before any ABL or long print:

1. `G28 X` — carriage must move toward the right endstop.
2. `G28 Y` — bed must move toward the rear endstop.
3. `G28 Z` — bed must move downward (away from the probe) until the probe triggers.
4. If any axis moves the wrong way, toggle its `INVERT_*_DIR`, recompile, and re-flash.

---

### Max feedrate

`DEFAULT_MAX_FEEDRATE { 500, 500, 10, 50 }` (mm/s — ceiling values, not print speeds)

| Axis | Value | Notes |
|------|-------|-------|
| X | 500 mm/s | Safe upper bound for TMC2209 microstepping on this frame. |
| Y | 500 mm/s | Moving-bed mass limits practical print speed to 100–150 mm/s well before this ceiling. |
| Z | 10 mm/s | Appropriate for a 4 mm lead screw. |
| E | 50 mm/s | Sufficient for PLA/PETG direct drive. |

---

### Max acceleration

`DEFAULT_MAX_ACCELERATION { 500, 500, 100, 5000 }` (mm/s²)

| Axis | Value | Notes |
|------|-------|-------|
| X | 500 mm/s² | Conservative; reduces ghosting. Raise to 1000–1500 mm/s² once ringing is characterised. |
| Y | 500 mm/s² | Upper edge for the stock moving-bed carriage. Lower to 300 mm/s² if layer shifts occur. |
| Z | 100 mm/s² | Standard for lead-screw Z. |
| E | 5000 mm/s² | Standard for direct-drive. Improves retraction sharpness at ≤ 2 mm retraction distances. |

Enabling `INPUT_SHAPING_X/Y` allows significantly higher X/Y acceleration after the resonant frequency is measured and compensated.

---

### Hotend PID

Run PID autotune before the first print — the firmware defaults are for a generic hotend and will oscillate with the E3D assembly:

```gcode
M303 E0 C8 S240   ; autotune at 240 °C, 8 cycles
M301 P<Kp> I<Ki> D<Kd>
M500
```

Replace `S240` with your typical printing temperature.



Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on Github, perform your modifications, and direct users to your modified fork.
