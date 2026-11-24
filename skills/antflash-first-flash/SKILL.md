# AntFlash First Flash

The end-to-end workflow: install AntFlash 32 from GitHub and complete a
first verified flash on a real board.

## Compatibility

- Boards: ESP32, ESP32-S2, ESP32-S3, ESP32-C3, ESP32-C5, ESP32-C6 — confirm
  your exact chip with the chip-family skill for your board before flashing.
- Browser: Chromium-based (Chrome, Edge, Brave) with Web Serial enabled.
- Cable: a USB **data** cable. Charge-only cables show no port.

## Setup

1. Clone the repo (see the root README) or open the hosted flasher.
2. Open `flasher.html`. The panel loads firmware manifests from the house
   catalog only.
3. Pick your board family in the panel. The family you pick arms the
   chip-family guard.

## Flash workflow

1. **Connect** — plug the board in, click Connect, pick the serial port.
2. **Identify** — the panel reads the chip family from the silicon. If it
   does not match the family you picked, the flash stops here.
3. **Choose a package** — pick from the catalog. Labeled stubs are refused;
   they carry no seated binary yet.
4. **Flash** — the panel writes the package at the manifest's offsets and
   shows progress per part.
5. **Verify** — the board reboots and the panel confirms the boot. A failed
   boot check sends you to your chip skill's recovery steps before anything
   else is attempted.

## Safety

- Never flash a package whose chip family differs from the connected board.
  The guard enforces this; do not work around it.
- Keep the board powered and the cable seated for the whole write. A cable
  bump mid-write is the most common cause of a bad flash.
- One board at a time per browser tab.

## Supported operations

- First flash of any live (non-stub) catalog package.
- Re-flash / recovery flash of the same package after a failed boot.
- Board identification read-back before any write.
