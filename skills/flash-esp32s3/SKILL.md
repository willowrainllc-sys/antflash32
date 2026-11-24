---
name: flash-esp32s3
description: "ESP32-S3 boards with native USB: direct Web Serial flashing, no bridge chip needed."
---

# Flash ESP32-S3

Flashing ESP32-S3 boards with AntFlash 32.

## Compatibility

- Chips: ESP32-S3 boards, including the S3 pod carriers used by the Ant
  Pod Firmware and the Anthony ASI Pod builds.
- Native USB: the S3 talks Web Serial directly — no USB-UART bridge chip
  required. Boards with both ports: use the native USB port for flashing.

## Setup

1. Connect to the native USB port with a data cable.
2. Open the flasher, pick the ESP32-S3 family, connect, and let the guard
   read the chip before choosing a package.

## Safety

- The S3's USB port re-enumerates after reset — if the port disappears
  mid-flow, reconnect in the panel rather than restarting the browser.
- PSRAM-equipped variants take the PSRAM builds where a manifest offers
  both; the manifest's build list is the authority.

## Supported operations

- Full-package flash of S3 catalog builds.
- Pod seating flashes (Ant Pod Firmware, Anthony ASI Pod when published).
- Recovery re-flash after a failed boot.
