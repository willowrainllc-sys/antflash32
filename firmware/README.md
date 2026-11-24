# Firmware Catalog Index

Every package the AntFlash 32 flasher can serve, in one index. The flasher
loads manifests from the house catalog only — never from third-party
flasher sites. Manifests use the standard shape: `name`, `version`,
`builds[]` with `chipFamily` and `parts[]` (`path`, `offset`).

**79 manifests total: 5 house + 12 Bit Pirate + 62 Super Library.**

Status words mean exactly this:

- **live slot** — the manifest is wired and its binary seats from the
  house build pipeline.
- **stub** — cataloged, no binary seated yet. The flasher visibly labels
  stubs and refuses to write them. A stub seats only with its license text
  and attribution attached, per the project's terms.

## House packages (Willow Rain Company LLC)

| Package | Manifest | Chips | Status |
|---|---|---|---|
| Ant Pod Firmware | `esp32-ant-esp32s3.json`, `esp32-ant-esp32.json` | S3, ESP32 | live slot |
| ANT_3SP Packages | `esp32-ant-esp32c5.json` | C5 | stub — no C5 binary until the house build seat produces it |
| Anthony ASI Pod | `anthony-asi-pod-esp32s3.json` | S3 | stub |
| Sensor Starter Pack | `sensor-starter-pack-esp32s3.json` | S3 | stub |

## ESP32 Bit Pirate (MIT — geo-tp and contributors)

One firmware build per board, every mode inside; the flagship and each
package entry seat the same per-board binary. All entries stub until
binaries seat with the MIT license text and attribution.

| Package | Manifests |
|---|---|
| ESP32 Bit Pirate (flagship) | `bit-pirate-esp32s3.json`, `bit-pirate-esp32c6.json` |
| Bit Pirate Bus Interface | `bit-pirate-bus-esp32s3.json`, `bit-pirate-bus-esp32c6.json` |
| Bit Pirate — Wireless | `bit-pirate-wireless-esp32s3.json`, `bit-pirate-wireless-esp32c6.json` |
| Bit Pirate — Modules & Chips | `bit-pirate-modules-esp32s3.json`, `bit-pirate-modules-esp32c6.json` |
| Bit Pirate — Web Tools | `bit-pirate-webtools-esp32s3.json`, `bit-pirate-webtools-esp32c6.json` |
| Bit Pirate — Automation | `bit-pirate-automation-esp32s3.json`, `bit-pirate-automation-esp32c6.json` |

## Super Library (open-source ESP32 firmware)

14 projects cataloged from repo evidence — license read from each project,
release binaries confirmed up<MASKED_USER_ID_001>eam. Every manifest is a stub; binaries
activate only when seated per each project's terms. GPL entries carry the
corresponding-source offer. Cataloged is **not** bench-verified.

| Project | Chips | License |
|---|---|---|
| ESPHome | ESP32 / S3 / C3 / C6 | GPL-3.0 |
| Tasmota | ESP32 / C2 / C3 / C5 / C6 / P4 / S2 / S3 | GPL-3.0 |
| ESPEasy | ESP32 / S2 / S3 / C3 / C6 / C2 | GPL-3.0+ |
| OpenMQTTGateway | ESP32 / C3 / S3 | GPL-3.0 |
| WLED | ESP32 / S2 / S3 / C3 | EUPL-1.2 |
| Retro-Go | ESP32 / S2 / S3 | GPL-2.0 |
| FujiNet | ESP32 / S3 | GPL-3.0 |
| CrossPoint Reader | C3 / S3 | MIT |
| Meshtastic | ESP32 / S3 / C3 / C6 | GPL-3.0 |
| ExpressLRS | ESP32 / C3 | GPL-3.0 |
| MicroPython | ESP32 / C2 / C3 / C5 / C6 / S2 / S3 / P4 | MIT |
| CircuitPython | ESP32 / S2 / S3 / C3 | MIT |
| ESP-AT | ESP32 / S2 / C2 / C3 / C6 / C5 | Espressif MIT |
| XiaoZhi AI Chatbot | ESP32 / C3 / C5 / C6 / S3 / P4 | MIT |

## Naming law

A package's display name is identical on its library card, in its
manifest's `name` field, and in the AntFlash 32 app list. If a surface
disagrees with this index, the surface is wrong and gets fixed to match.
