---
name: flash-esp32c6
description: "ESP32-C6 boards: Web Serial flashing and the bus-expander package set with AntFlash 32."
---

# Flash ESP32-C6

Flashing ESP32-C6 boards with AntFlash 32.

## Compatibility

- Chips: ESP32-C6 boards, including the C6 bus-expander carrier used by
  the Bit Pirate package set.
- Connect over the board's USB serial port with a data cable.

## Setup

1. Connect the board; open the flasher and pick the ESP32-C6 family.
2. Let the guard read the chip, then choose the package.

## Safety

- C6 and C5 packages are not interchangeable even though the boards look
  alike on a bench. The chip-family guard is the check — trust the
  read-back, not the silkscreen.
- Bus-expander work happens on your own bench hardware only (see the Bit
  Pirate bus tools skill).

## Supported operations

- Full-package flash of C6 catalog builds.
- The Bit Pirate C6 package set (flagship, bus, wireless, modules, web
  tools, automation) as its binaries seat.
- Recovery re-flash after a failed boot.
