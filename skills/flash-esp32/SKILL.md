# Flash ESP32 (Classic)

Flashing the original ESP32 with AntFlash 32.

## Compatibility

- Chips: ESP32 (original, dual-core) boards, including most dev-kit and
  module carriers.
- Download mode: hold BOOT while tapping EN/RESET on most dev boards;
  some carriers auto-enter download mode over serial — the flasher detects
  either.

## Setup

1. Data USB cable to the board's UART port (not a native-USB port on
   dual-port boards).
2. Open the flasher and pick the ESP32 family; connect and let the guard
   read the chip.

## Safety

- A board that will not enter download mode is a cable or driver problem
  until proven otherwise — swap the cable before suspecting the silicon.
- Erasing flash wipes the running firmware. Confirm the package first;
  there is no undo after the write starts.

## Supported operations

- Full-package flash from the house catalog (Ant Pod Firmware and the
  cataloged open-source builds for this family).
- Recovery re-flash after a failed boot.
