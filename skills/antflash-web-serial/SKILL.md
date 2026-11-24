---
name: antflash-web-serial
description: "The shared flashing core every chip skill rides on: manifest loading, chip-family guard, write, and boot verification."
---

# AntFlash Web Serial Protocol

The shared flashing core. Every chip-family skill rides on this protocol;
it defines how manifests load, how the chip guard works, and how a flash is
verified.

## Compatibility

- Any ESP32-family target supported by a chip-family skill in this catalog.
- Host side: Web Serial in a Chromium-based browser. No native helper, no
  driver install, no command-line tools.

## The manifest

The flasher loads manifests from the house catalog only — never from
third-party flasher sites. Standard manifest shape:

- `name`, `version`
- `builds[]`, each with a `chipFamily` and `parts[]` (`path`, `offset`)
- `"stub": true` marks a package with no seated binary. The flasher refuses
  stubs visibly; it never writes one silently.

## Protocol steps

1. **Load** the manifest for the chosen package.
2. **Connect** over Web Serial and read the target's chip family from the
   silicon itself — never from the board's label or the user's pick.
3. **Guard** — compare the silicon family against every build in the
   manifest. No matching build, no write.
4. **Write** each part at its manifest offset, with per-part progress.
5. **Verify** — reset the target and confirm the boot over the same serial
   session. The flash is not "done" until the boot check passes.

## Safety

- The guard reads the chip; it does not trust selections. Any future change
  that weakens this is a breaking change to the whole system.
- A manifest from outside the house catalog is never loaded, even if its
  format matches.
- Serial is a single-owner resource: one flasher session per port.

## Supported operations

- Manifest load and validation.
- Chip identification and family guard.
- Offset-accurate multi-part writes.
- Post-write boot verification.
