# Firmware Library

The house firmware catalog — what the flasher can serve, where each package
comes from, and whether it is live or a labeled stub.

## Compatibility

- Catalog size: **79 manifests** — 5 house packages, 12 Bit Pirate
  packages, 62 Super Library packages across 14 open-source projects.
- Every entry is a standard manifest (`name`, `version`, `builds[]` with
  `chipFamily` and `parts[]`). The index of record is `firmware/README.md`
  in this repo.

## The collections

- **House (Muse Repo)** — Ant Pod Firmware (S3 + classic, live slots),
  ANT_3SP Packages (C5, stub), Anthony ASI Pod (S3, stub), Sensor Starter
  Pack (S3, stub).
- **ESP32 Bit Pirate** — MIT-licensed bus-tool firmware; one build per
  board with every mode inside. Flagship plus Bus Interface, Wireless,
  Modules & Chips, Web Tools, and Automation entries for S3 and C6. All
  stub until binaries seat with license text and attribution.
- **Super Library** — ESPHome, Tasmota, ESPEasy, OpenMQTTGateway, WLED,
  Retro-Go, FujiNet, CrossPoint Reader, Meshtastic, ExpressLRS,
  MicroPython, CircuitPython, ESP-AT, XiaoZhi. Licenses read per project
  (GPL family, EUPL-1.2, MIT) and recorded in the index. All stub until
  seated per each project's terms; GPL entries carry the
  corresponding-source offer.

## Safety

- Cataloged is not bench-verified. A package earns a flash recommendation
  only after the house verify-flash plan runs it on real hardware.
- A package's display name is identical on its library card, in its
  manifest, and in the app list. If a surface disagrees, the surface is
  wrong.
- The flasher refuses stubs. Seating a binary without its license text is
  a catalog defect, not a shortcut.

## Supported operations

- Browse and search the catalog by chip family and collection.
- License and status lookup per package.
- Manifest hand-off to the AntFlash Web Serial protocol for live packages.
