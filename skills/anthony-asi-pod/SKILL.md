---
name: anthony-asi-pod
description: "The ESP32-S3 pod build that carries the Anthony ASI gateway client. Binary not yet published; skill covers the target spec and seating checklist."
---

# Anthony ASI Pod

The ESP32-S3 pod build that carries the Anthony ASI gateway client — a pod
that can ask the house brain and act on the answer at the edge.

## Compatibility

- Hardware: ESP32-S3 carrier (see the Flash ESP32-S3 skill for seating).
- Status: **binary not yet published.** The Anthony ASI Pod manifest in
  the firmware catalog is a labeled stub; the flasher refuses it until the
  build publishes. This skill covers the target spec and the seating
  checklist so the publish is a one-step event.

## Target spec

- Gateway client to Anthony ASI (chat completions + health endpoints),
  configured per seat.
- Pod law applies in full: senses and bridge on the pod, thinking on the
  brain side, commands validated before the pod acts.
- House Wi-Fi join at first boot; tailnet seating per the ANT_3SP pattern
  where the build supports it.

## Seating checklist (at publish)

1. Binary built from the ESP32-ANT package and hash-recorded.
2. Manifest stub flag removed only after the binary is seated with its
   license and attribution.
3. First flash verified on a bench S3 before the package is announced.
4. Catalog line updated from stub to live in `firmware/README.md`.

## Safety

- A stub is a promise, not a product: nothing in this skill claims the pod
  build exists until the checklist above is complete.
- Credentials seat on the build machine only, never in this repo.

## Supported operations

- None until publish. After publish: gateway ask/answer and
  brain-validated edge tasks, per the target spec.
