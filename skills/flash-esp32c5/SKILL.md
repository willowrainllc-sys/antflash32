# Flash ESP32-C5

Flashing ESP32-C5 boards with AntFlash 32 — including the ANT_3SP pod
target.

## Compatibility

- Chips: ESP32-C5 (RISC-V, dual-band Wi-Fi 6, BLE 5).
- Primary house target: the sealed Home Link puck that becomes ANT_3SP.
  That unit has USB-Serial-JTAG only — no GPIO breakouts, no display —
  and this skill treats it as a sealed bridge, never as a dev board.

## Setup

1. Connect over USB. The C5 presents USB-Serial-JTAG directly.
2. Open the flasher, pick the ESP32-C5 family, connect, and let the guard
   read the chip.

## Safety

- **Guarded flash packet only.** The ANT_3SP conversion flash runs from
  the house flash packet, which reads the chip and flash size back with
  esptool before any write and gates on that read-back. Flashing the pod
  replaces its bridge firmware — there is no stock-firmware return path,
  and the packet says so before it writes.
- No C5 house binary is published yet: the ANT_3SP Packages manifest is a
  labeled stub until the house build seat produces the binary, and the
  flasher refuses it until then.
- Power note: a pod powered from a sleeping host is a pod that is down.
  Seat converted pods on an always-on USB source.

## Supported operations

- Identification and read-back of C5 targets.
- Catalog flashes for C5 builds as they publish (Tasmota, MicroPython,
  ESP-AT, and XiaoZhi families are cataloged for this chip).
- The ANT_3SP conversion flash, via the guarded packet, once its binary
  publishes.
