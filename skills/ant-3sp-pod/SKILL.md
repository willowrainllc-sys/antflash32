# ANT_3SP Pod

The third-controller pod: an ESP32-C5 node that senses, bridges, and relays
for the house brains — Anthony ASI on the Dell seat and Muse on the
rig/cloud seat.

## Compatibility

- Hardware: ESP32-C5 unit with ~8 MB flash and PSRAM (the house unit
  verified ~7.8 MB free PSRAM before conversion). Single-core RISC-V at
  240 MHz, dual-band Wi-Fi 6, BLE 5.
- The pod is a controller node, not a third host: it runs no operating
  system and no language model. The brains think; the pod executes
  delegated tasks after brain validation — standing house pod law.

## Setup

1. Convert the unit with the guarded flash packet (see the Flash ESP32-C5
   skill): esptool read-back first, write second, no exceptions.
2. Seat the pod's configuration on the build machine only — Wi-Fi and
   tailnet credentials live in the git-ignored device config, never in
   this repo.
3. The pod joins the house Wi-Fi and the tailnet as its own node
   (hostname `ant-3sp`), then registers with the Anthony ASI gateway.

## What it carries

- **Gateway client** — talks to the Anthony ASI gateway (chat completions
  + health) so the pod can ask a brain and hear back.
- **Its own control API** — status, say, and housekeeping endpoints the
  brains reach it by.
- **OTA receive / stage / relay** — receives a firmware image for a
  sibling pod, stages it in PSRAM (one image at a time; a reboot clears
  the stage by design), validates hash + task with a brain, then relays.

## Safety

- The pod never originates fleet actions on its own initiative. Every
  consequential task is validated by a brain first.
- VPN fallback is never silent: if the tailnet client will not fit the
  C5 build, the pod falls back to a WireGuard client through a house
  gateway and the substitution is reported with the compile evidence.
- Dell asleep = pod down, until the pod is seated on an always-on USB
  source.

## Supported operations

- House endpoint health checks on cadence, with mesh heartbeat posts.
- Sibling-pod status polling across the ESP32-ANT fleet.
- Brain-validated relay of firmware images to sibling pods.
- Status and say endpoints for the house brains.
