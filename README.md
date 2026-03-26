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

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `INVERT_X_DIR` | `false` | `true` | Matches the physical motor wiring on the Ender-5 X axis. |
| `INVERT_Z_DIR` | `false` | `true` | Matches the physical motor wiring on the Ender-5 Z axis. |
| `INVERT_E0_DIR` | `false` | `true` | Matches the physical motor wiring of the direct-drive extruder. |

#### Probe type and offset

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `FIX_MOUNTED_PROBE` | disabled | **enabled** | Declares a probe that is permanently fixed to the carriage (no deploy/stow mechanism). Required for `AUTO_BED_LEVELING_BILINEAR` — without a probe type defined the sanity checker refuses to build. |
| `NOZZLE_TO_PROBE_OFFSET` | `{ 10, 10, 0 }` | `{ -48, -10, 0 }` | Offset measured for the probe mount used on this printer. |

#### Bed geometry

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `X_BED_SIZE` / `Y_BED_SIZE` | `200` | `220` | The Ender-5 has a 220 × 220 mm printable area. |
| `Z_MAX_POS` | `200` | `300` | The Ender-5 Z travel is 300 mm. |

#### Auto Bed Leveling

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `AUTO_BED_LEVELING_BILINEAR` | disabled | **enabled** | Enables bilinear mesh leveling with the fixed probe. |
| `GRID_MAX_POINTS_X` | `3` | `5` | 5 × 5 = 25-point mesh for better leveling accuracy across the 220 mm bed. |
| `MULTIPLE_PROBING` | disabled | `2` | Probes each mesh point twice and averages the results, reducing the effect of electrical noise or minor surface contamination on the mesh. |
| `Z_SAFE_HOMING` | disabled | **enabled** | Moves XY to the probe position before homing Z, preventing the nozzle from contacting the bed at an unprobed corner. Required when using a fixed probe — Marlin raises a build error if this is omitted. |

#### Display

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `DISPLAY_CHARSET_HD44780` | `JAPANESE` | `WESTERN` | Displays Latin characters correctly on the CR-10 stock display. |
| `CR10_STOCKDISPLAY` | disabled | **enabled** | The Ender-5 uses the CR-10 stock display (EXP1 connector). |
| `ENCODER_PULSES_PER_STEP` | disabled | `4` | The CR-10 stock rotary encoder generates 4 pulses per detent. Without this, each menu item requires turning the knob 4 steps instead of 1. |
| `ENCODER_STEPS_PER_MENU_ITEM` | disabled | `1` | Pairs with `ENCODER_PULSES_PER_STEP` so one physical click advances exactly one menu item. |
| `EEPROM_SETTINGS` | disabled | **enabled** | Allows saving configuration to flash with `M500`. Without this, the ABL mesh, Z offset, PID values and all runtime settings revert to firmware defaults on every power cycle, making ABL completely ineffective. |
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
| `HYBRID_THRESHOLD` | disabled | **enabled** | Automatically switches from silent StealthChop to spreadCycle above the configured speed threshold (X/Y: 100 mm/s, Z: 3 mm/s, E: 30 mm/s), combining quiet low-speed printing with full torque at high speed. |
| `TMC_DEBUG` | disabled | **enabled** | Enables the `M122` G-code command to report live driver parameters (current, temperature, stallguard value) — useful for diagnostics. |
| `DIAG_JUMPERS_REMOVED` | undefined | **defined** | Suppresses the build warning that fires when `SENSORLESS_HOMING` is disabled on a board that has DIAG pins wired to the endstop header. The SKR Mini E3 V3.0 routes DIAG signals through removable jumpers; with physical endstops in use those jumpers must be removed to avoid false triggers, and this define confirms that has been done. |

#### Probing and first-layer adjustment

| Setting | Stock value | New value | Reason |
|---|---|---|---|
| `BABYSTEPPING` | disabled | **enabled** | Allows adjusting the Z offset in real time while printing via the LCD menu, without stopping the print. Essential for dialling in the first layer after an ABL calibration. |
| `BABYSTEP_ZPROBE_OFFSET` | disabled | **enabled** | Links babystepping to the `M851` Z probe offset. Adjustments made during a print are reflected in the stored offset so the change persists after `M500`. |

---

## Optional Features (not enabled)

The following settings were reviewed but left at their stock (disabled) values. Each one is a genuine improvement for this printer, but requires either additional hardware, per-filament calibration, or physical measurement before it can be used safely. Enable them when you are ready to go through the corresponding setup steps.

### `Marlin/Configuration.h`

#### Bed temperature control

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `PIDTEMPBED` | Uncomment `#define PIDTEMPBED` | Switches the heated bed from bang-bang (full-on / full-off) to closed-loop PID control, giving tighter temperature stability and reducing power-supply ripple. | After enabling, run `M303 E-1 C8 S60` (autotune at 60 °C for 8 cycles), then `M500` to save. Re-tune whenever you change the bed surface or insulation. |

#### Motion quality

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `S_CURVE_ACCELERATION` | Uncomment `#define S_CURVE_ACCELERATION` | Replaces the trapezoidal velocity profile with a smooth S-curve, reducing the jerk at the start and end of acceleration phases. Lowers ringing without needing to reduce speed. | None — enable and test. If artefacts appear, disable and investigate acceleration values first. |

### `Marlin/Configuration_adv.h`

#### Extrusion quality

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `LIN_ADVANCE` | Uncomment `#define LIN_ADVANCE` and set `LIN_ADVANCE_K 0` as a starting point | Compensates for pressure build-up in the nozzle at the start and end of lines, reducing blobs at corners and improving dimensional accuracy on perimeters. | Requires per-filament K-factor calibration using the [Marlin LA calibration pattern](https://marlinfw.org/tools/lin_advance/k-factor.html). A wrong K value makes print quality worse, so do not enable without calibrating. |

#### Resilience

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `POWER_LOSS_RECOVERY` | Uncomment `#define POWER_LOSS_RECOVERY` in `Configuration_adv.h` | Saves print state to the SD card periodically so a print can be resumed after a power cut or accidental reset. | Requires `SDSUPPORT` (already enabled). The Ender-5 Z lead screw must not back-drive under gravity when power is cut — verify this before relying on recovery, otherwise the nozzle will crash into the print on resume. |
| `FILAMENT_RUNOUT_SENSOR` | Uncomment `#define FILAMENT_RUNOUT_SENSOR` | Pauses the print and parks the head when the filament sensor detects a runout or break. | Requires a filament runout sensor wired to the dedicated pin on the SKR Mini E3 V3.0 (`E0-STOP` header). Also requires `ADVANCED_PAUSE_FEATURE` (see below). |
| `ADVANCED_PAUSE_FEATURE` | Uncomment `#define ADVANCED_PAUSE_FEATURE` | Enables the guided filament-change (`M600`) and park-on-pause workflows used by runout recovery and manual colour changes. | No additional hardware needed, but `NOZZLE_PARK_FEATURE` must also be enabled. Configure `FILAMENT_CHANGE_UNLOAD_LENGTH` and `FILAMENT_CHANGE_LOAD_LENGTH` to match your bowden/direct-drive path length. |

#### Resonance compensation

| Setting | How to enable | What it does | Setup required |
|---|---|---|---|
| `INPUT_SHAPING_X` / `INPUT_SHAPING_Y` | Uncomment both `#define INPUT_SHAPING_X` and `#define INPUT_SHAPING_Y` in `Configuration_adv.h` | Applies a notch filter to cancel the printer's resonant frequency on each axis, greatly reducing ringing (ghosting) artefacts at higher speeds. Supported on the STM32G0B1 MCU of the SKR Mini E3 V3.0. | Requires measuring the resonant frequency of each axis. The easiest method is to print a ringing test tower and read the frequency from the pattern, or attach an ADXL345 accelerometer and run `M593` resonance measurement. Set `SHAPING_FREQ_X` and `SHAPING_FREQ_Y` to the measured values before enabling. |

---

## Calibration Reference

This section explains the origin of each calibration value in the firmware, identifies what is mathematically confirmed, what is empirically calibrated and should be re-verified on the new board, and what must be measured from scratch.

### Steps per mm

#### X and Y axes — GT2 belt / 20-tooth pulley / TMC2209

The theoretical steps/mm for GT2 timing belt with a 20-tooth pulley is:

```
Steps/mm = (motor steps/rev × microstepping) / (pulley teeth × belt pitch)
         = (200 × 16) / (20 × 2 mm)
         = 3200 / 40
         = 80.000 steps/mm
```

The firmware uses `79.50` (X) and `79.80` (Y), which are 0.625 % and 0.25 % below the theoretical value respectively. This is normal: minor variation in belt tension, actual pulley pitch diameter, and GT2 tooth geometry routinely shift the true value by ±1 %. These numbers were measured on the previous SKR 1.4 Turbo board and are likely correct, but should be re-verified after assembly using the standard 100 mm extrusion calibration procedure:

1. Mark a reference point on the belt or measure axis position with a calliper.
2. Command `G0 X100` (or Y100) from a known origin.
3. Measure actual travel. New steps/mm = `current_steps × 100 / actual_mm`.
4. Save with `M92 X<value> Y<value>` then `M500`.

#### Z axis — TR8×4 lead screw (4 mm lead, 8 mm pitch)

```
Steps/mm = (motor steps/rev × microstepping) / lead
         = (200 × 16) / 4 mm
         = 3200 / 4
         = 800.000 steps/mm
```

The firmware value `800` is **mathematically exact**. No re-verification is required unless the lead screw is replaced.

> Note: "TR8×4" means 8 mm pitch, 2 starts, 4 mm lead. Confirm the lead screw spec if in doubt — a TR8×8 screw (8 mm lead, single start) would require 400 steps/mm instead.

#### E axis (extruder) — direct drive MK8 gear

The firmware uses `93 steps/mm`. Back-calculating the effective drive gear diameter:

```
Circumference = (motor steps/rev × microstepping) / steps_per_mm
              = (200 × 16) / 93
              = 34.41 mm/rev

Effective diameter = circumference / π = 34.41 / 3.1416 ≈ 10.95 mm
```

A 10.95 mm effective diameter is consistent with a standard Creality MK8 drive gear (~11 mm). This is a calibrated value from the previous board and is a reasonable starting point, but **must be re-verified physically** before printing, because:

- The actual grip point on an MK8 gear depends on filament diameter and the exact gear profile.
- TMC2209 microstepping interpolation is handled identically to the previous board, so the value should transfer, but extruder calibration takes only 10 minutes and eliminates a major source of under/over-extrusion.

**E-steps calibration procedure:**

1. Mark the filament 100 mm and 120 mm from the extruder entry point.
2. Command `G1 E100 F100` (cold — release tension first).
3. Measure the distance from the entry point to the remaining mark. Actual extruded = 120 mm − remaining distance.
4. New E steps = `93 × 100 / actual_mm`. Save with `M92 E<value>` then `M500`.

---

### Probe offsets

#### X offset: −48 mm

The probe is mounted 48 mm to the left of the nozzle. This has a direct effect on bed coverage:

```
Probe can reach X_MIN when nozzle is at: X_MIN_POS + 48 = 0 + 48 = 48 mm
Probe can reach X_MAX when nozzle is at: X_MAX_POS − 0 = 220 mm → probe reaches 220 − 48 = 172 mm

Probed X range: [48 → 172] = 124 mm
Unprobed right strip: 220 − 172 = 48 mm (21.8 % of bed width)
```

> The right ~48 mm strip is not directly sampled. Marlin extrapolates the mesh beyond the probed area using the gradient of the nearest measured points. This is usually acceptable, but if the right edge of your first layer looks different from the centre, physically re-centering the probe mount (or shifting the mesh inward) is the correct fix.

**The Z offset must always be measured fresh** — it depends on the exact mounting height of the probe above the nozzle. Run `M851 Z0`, deploy manually, home Z, then use `BABYSTEP_ZPROBE_OFFSET` (or `M851 Z<value>` + `M500`) to dial in the offset until a sheet of paper drags with light resistance under the nozzle.

#### Y offset: −10 mm

The probe is 10 mm in front of the nozzle. Y coverage:

```
Probe can reach Y_MIN when nozzle is at: 0 + 10 = 10 mm
Probe can reach Y_MAX when nozzle is at: 220 mm → probe reaches 220 − 10 = 210 mm

Probed Y range: [10 → 210] = 200 mm (full bed depth minus 10 mm margins)
```

Y coverage is complete. No extrapolation required.

#### Z offset: 0 (placeholder)

The Z offset in the firmware (`NOZZLE_TO_PROBE_OFFSET` Z component) is `0` and is a **placeholder only**. The actual value must be measured on the physical printer as described above.

---

### Motor directions

All four axes are set to `INVERT_*_DIR true`. These values were carried over from the previous SKR 1.4 Turbo build. **Verify all directions on first boot before any ABL or long print:**

1. Home each axis individually: `G28 X`, `G28 Y`, `G28 Z`.
2. Watch that the motor moves toward the endstop, not away.
3. If an axis moves the wrong way, toggle its `INVERT_*_DIR` in `Configuration.h`, recompile, and re-flash.
4. Never command an axis to move without watching it — a wrong direction on Z can crash the nozzle into the bed.

---

### Max feedrate

`DEFAULT_MAX_FEEDRATE { 500, 500, 10, 50 }` (mm/s for X, Y, Z, E)

These are **ceiling values** — the printer will never exceed them regardless of what the slicer requests. They do not affect print speed directly; actual print speed is set in the slicer.

| Axis | Value | Assessment |
|------|-------|-----------|
| X | 500 mm/s | Very conservative ceiling; a 220 mm Ender-5 X axis can physically move faster, but 500 mm/s is a safe upper bound for TMC2209 microstepping. |
| Y | 500 mm/s | Same as X. The moving-bed mass on the Y axis means print speeds above 100–150 mm/s will cause quality degradation long before hitting this ceiling. |
| Z | 10 mm/s | Appropriate for a 4 mm lead screw. The Ender-5 Z typically travels at 5–7 mm/s during probing; 10 mm/s is a safe ceiling. |
| E | 50 mm/s | Sufficient for PLA/PETG direct drive. High-speed retraction testing should be done gradually. |

---

### Max acceleration

`DEFAULT_MAX_ACCELERATION { 500, 500, 100, 5000 }` (mm/s² for X, Y, Z, E)

| Axis | Value | Assessment |
|------|-------|-----------|
| X | 500 mm/s² | Conservative; reduces ghosting on the Ender-5 frame. Increase to 1000–1500 mm/s² if print speed is raised and no ringing artefacts appear. |
| Y | 500 mm/s² | The moving bed is the heaviest axis. 500 mm/s² is at the upper edge for a stock Ender-5 bed carriage — watch for layer shifts on aggressive curves. Lower to 300 mm/s² if layer shifts occur; raise to 800 mm/s² only after confirming belt tension and idler bearings. |
| Z | 100 mm/s² | Standard for a lead-screw Z. No reason to change. |
| E | 5000 mm/s² | Standard for direct-drive. High E acceleration improves retraction sharpness without stressing the extruder mechanism at typical retraction distances (≤ 2 mm). |

**Calibration note:** If you enable `INPUT_SHAPING_X/Y` (see Optional Features), you can safely raise X/Y acceleration significantly after measuring and compensating the resonant frequency.

---

### Hotend PID

The firmware uses Marlin's stock default PID values (`DEFAULT_Kp`, `DEFAULT_Ki`, `DEFAULT_Kd`) inherited from the configuration example. These were tuned for a different hotend and may cause temperature oscillation with the E3D assembly.

**Run PID autotune before printing:**

```gcode
M303 E0 C8 S240   ; autotune hotend at 240°C, 8 cycles
```

When the cycle completes, Marlin prints the recommended P/I/D values. Apply them with:

```gcode
M301 P<Kp> I<Ki> D<Kd>
M500
```

Replace `S240` with your typical printing temperature.



Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on Github, perform your modifications, and direct users to your modified fork.
