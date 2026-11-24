# Skill Catalog


13 active skills: four chip-family skills, two pod skills, two shared-protocol skills, two setup skills, one firmware-library skill, one bench-tool skill, and one read-only inspection skill.

Pick the skill that matches your board or pod — each one carries its chip compatibility, setup steps, safety notes, and the operations it supports.


## Gadget setup


- [Ant wake word setup](ant-wake-word-setup/SKILL.md) — build the native detector library from this repo checkout and verify it locally on your own machine before opting in to microphone use. Multilingual from the start: the Spanish wake call "Hola Antonio" is confirmed; the English, French, and Portuguese variants are OWNER-PICK-PENDING.

- [AntFlash first flash](antflash-first-flash/SKILL.md) — install from GitHub, connect a board over Web Serial, and complete a first verified flash end to end.


## Shared protocol


- [AntFlash Web Serial protocol](antflash-web-serial/SKILL.md) — the shared flashing core every chip skill rides on: manifest loading, chip-family guard, write, and boot verification.

- [Hand of God](hand-of-god/SKILL.md) — unified control across every house ecosystem — web, mobile, tablet, desktop, and pods — one control hand per house agent, riding the house mesh. Spec in flight.


## Chip families


- [Flash ESP32 (classic)](flash-esp32/SKILL.md) — original ESP32 boards: download mode, manifest flashing, and boot verify.

- [Flash ESP32-S3](flash-esp32s3/SKILL.md) — S3 boards with native USB: direct Web Serial flashing, no bridge chip needed.

- [Flash ESP32-C5](flash-esp32c5/SKILL.md) — C5 boards including the ANT_3SP pod target: dual-band parts, guarded flash packet only.

- [Flash ESP32-C6](flash-esp32c6/SKILL.md) — C6 boards: Web Serial flashing and the bus-expander package set.


## Pods and firmware families


- [ANT_3SP pod](ant-3sp-pod/SKILL.md) — the third-controller pod: ESP32-C5 node that senses, bridges, and relays for the house brains; executes only brain-validated tasks.

- [Anthony ASI Pod](anthony-asi-pod/SKILL.md) — the S3 pod build that carries the Anthony ASI gateway client. Binary not yet published; skill covers the target spec and seating checklist.

- [Firmware library](firmware-library/SKILL.md) — the house firmware catalog: 79 manifests across house, bus-tool, and open-source collections, each with license and live/stub status.


## Bus and bench tools


- [Bit Pirate bus tools](bit-pirate-bus-tools/SKILL.md) — UART, SPI, I2C, and 1-Wire bus work on your own bench hardware, from the house tool catalog; attack-class modes are excluded by house rule.


## Read-only inspection


- [Flash dump inspector](flash-dump-inspector/SKILL.md) — read-only: read back a board's flash, compare it against a manifest, and report differences. Never writes.
