# M1: Dumb watch feature parity

The focus for M1 is to get WASP both to meet feature parity with a dumb
watch and to have a bootloader and watchdog strategy that is robust enough
to allow a PineTime case to be confidently glued shut.

## Bootloader

 * [X] Basic board ports (PineTime, DS-D6, 96Boards Nitrogen)
 * [X] OTA application update
 * [X] Enable watchdog before starting the application
 * [X] Splash screen
 * [X] Ignore start button for first few seconds
  
## MicroPython

 * [X] Basic board ports (PineTime, DS-D6, 96Boards Nitrogen)
 * [X] Long press reset (conditional feeding of the watchdog)
   - [X] Feed dog from REPL polling loop
   - [X] Feed dog from a tick interrupt
 
## WASP

 * [X] Display driver
   - [X] Display initialization
   - [X] Bitmap blitting
   - [X] RLE coder and decoder
   - [X] Optimized RLE inner loops
 * [X] Backlight driver
 * [X] Button driver (polling)
 * [X] Battery/charger driver
 * [X] Simple clock and battery level application
 * [X] Basic (WFI) power saving
 * [X] Implement simple RTC for nrf52

# M2: Great developer experience

The focus for M2 is to make development faster and easier by providing
a file system and file transfer code. This allows much faster
development cycles compared to full downloads of frozen modules.
Additionally support for multiple event-driven applications will be
added during M2 to further help developers by providing example
applications.

## Bootloader

 * [ ] OTA bootloader update
 * [ ] Stay in bootloader after battery run down
 * [ ] Implement power off support (no splash screen)
 * [ ] RTC time measurement whilst in bootloader

## MicroPython

 * [X] SPI FLASH driver
 * [X] Enable LittleFS on SPI FLASH (at boot)
 * [X] BLE file transfer
 * [ ] Full power saving

## WASP

 * [X] Add dd/mm/yyyy support to RTC
 * [ ] Button driver (interrupt based)
 * [ ] Touch sensor driver
 * [ ] Event driven application framework
 * [ ] Stopwatch app
 * [ ] Settings app
 * [X] PC-hosted simulation platform
 * [ ] Documentation
   - [ ] Sphinx framework and integration with github.io
   - [ ] Document bootloader protocols
   - [ ] Write full docstring documentation for all WASP components

# M3: Smartwatch

At M3 we start to build out full fitness tracking and notification
functionality.

## WASP

 * [ ] Enable heart rate sensor
   - [ ] HRS3300 driver
   - [ ] HRS data post-processing
   - [ ] Heart rate counter app
 * [ ] Notifications
   - [ ] BLE notification protocol
   - [ ] Notification popups
   - [ ] Notification app (show notification history)
   - [ ] Find a recommended Android app
 * [ ] Step counting
   - [ ] BMA421 driver
   - [ ] Step counter app
