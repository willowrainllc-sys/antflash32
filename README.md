# AntFlash 32

**Flash an ESP32 from your browser. No installs, no drivers to hunt down, no command line.**

AntFlash 32 is the Willow Rain Company LLC web flasher and skill system for the
Ant 32 line of ESP32 pods. Pick a board, plug it in over USB, choose a firmware
package, and AntFlash writes it and verifies the boot — the whole flow runs in
the browser over Web Serial.

This repository is the install point for the system: the flasher, the firmware
catalog index, and the community skill library that teaches the house agents
how each board and pod is set up, flashed, and safely operated.

---

## Install from GitHub

1. **Clone this repo** (or download the ZIP from the green **Code** button):

   ```bash
   git clone https://github.com/willowrainllc-sys/antflash32.git
   ```

2. **Open the flasher.** Serve the folder with any static file server and open
   `flasher.html` — or use the hosted flasher on the AntFlash 32 site. Web
   Serial needs a Chromium-based browser (Chrome, Edge, Brave) and a **data**
   USB cable; charge-only cables will not show a port.

3. **Flash.** Pick your board family, connect, choose a firmware package from
   the catalog, and flash. AntFlash checks the chip family before it writes a
   single byte and refuses any package that does not match your silicon.

That is the whole install. Skills, firmware, and guides all live in this repo
and update with a `git pull`.

## What's inside

| Path | What it is |
|---|---|
| `skills/` | The community skill library. Start with [`skills/CATALOG.md`](skills/CATALOG.md) — every skill is listed there by category. |
| `firmware/` | The firmware catalog index: every package the flasher can serve, with license and status. |
| `COMMUNITY.md` | How to contribute a skill of your own. |
| `LICENSE` | MIT. Use it, fork it, build on it. |

## The skills

Each skill covers one board family, pod, or shared protocol: chip
compatibility, setup, safety, and the operations it supports. The catalog
mirrors the layout the house uses everywhere — find your hardware in
[`skills/CATALOG.md`](skills/CATALOG.md), open its `SKILL.md`, and follow it
top to bottom.

Highlights:

- **Ant wake word setup** — the house wake-word detector, built locally from
  this checkout and verified on your machine before the microphone ever
  turns on. Multilingual from the start.
- **ANT_3SP pod** — the third-controller pod build: an ESP32-C5 node that
  senses, bridges, and relays for the house brains.
- **Hand of God** — unified control across every house ecosystem: web,
  mobile, tablet, desktop, and pods, riding the house mesh. *(Spec in
  flight.)*

## Firmware

The flasher serves packages from house manifests only — never from
third-party flasher sites. The catalog index in [`firmware/`](firmware/)
lists every package with its license, its source, and whether its binary is
live or still a labeled stub. Stub packages are refused by the flasher until
their binaries are seated with license text and attribution, per each
project's terms.

## Safety

- AntFlash flashes **your own boards**. The chip-family guard exists so a
  package built for one chip can never be written to another.
- Every flash is verified: if the boot check fails, the skill for your board
  walks you through recovery before anything else.
- Nothing in this repo attacks other people's networks or devices. The bus
  and wireless tooling is for your own hardware, on your own bench.

## Community

Skills are how this system grows. If you have a board, a pod build, or a
workflow worth teaching, see [`COMMUNITY.md`](COMMUNITY.md) — fork, add your
skill folder, register it in the catalog, and open a pull request.

---

*AntFlash 32 · ANT_3SP · Ant 32 — designed and built by Willow Rain Company
LLC. An independent house project; not affiliated with Espressif or any
up<MASKED_USER_ID_001>eam firmware project cataloged in `firmware/`.*
