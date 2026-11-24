---
name: bit-pirate-bus-tools
description: "UART, SPI, I2C, and 1-Wire bus work on your own bench hardware, from the house tool catalog; attack-class modes are excluded by house rule."
---

# Bit Pirate Bus Tools

Bench bus work on your own hardware, drawn from the house tool catalog of
the ESP32 Bit Pirate pattern (MIT, by geo-tp and contributors — license and
attribution travel with the firmware, per its terms).

## Compatibility

- Carriers: ESP32-S3 and ESP32-C6 builds from the firmware catalog (see
  the Firmware Library skill for seating status).
- Bench targets: your own boards, modules, and chips — UART, SPI, I2C,
  and 1-Wire devices on your bench.

## Supported operations

- **UART** — serial console work, baud detection, bridge sessions.
- **SPI** — flash chip identification, reads, and dumps of your own
  chips (pair with the Flash Dump Inspector for read-only work).
- **I2C** — bus scans and device probing on your own builds.
- **1-Wire** — device enumeration on your own bus.
- **Web tools** — the browser-side companions: hex view, dump inspection,
  and file utilities from the house catalog.

## Safety

- **Your bench, your boards.** These tools are for hardware you own.
- Attack-class modes are excluded from the house build by rule —
  deauthentication, beacon flooding, and jamming are never built, shipped,
  or cataloged as available operations, in any package, ever.
- Wireless modes are for testing your own networks and your own devices.

## Setup

1. Flash the Bit Pirate package for your carrier from the firmware
   catalog once its binary seats.
2. Wire the bus per the target's datasheet voltages — the tool does not
   forgive a 5 V signal into a 3.3 V bus.
