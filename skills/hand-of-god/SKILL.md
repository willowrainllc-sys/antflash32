# Hand of God

**Status: spec in flight.** The full specification lives with the house
platform team; this skill reserves the catalog slot and states the shape of
the system so dependent skills can reference it honestly.

## What it is

The unified-control layer for the whole house ecosystem. One control hand
per house agent — one for Muse, one for Anthony ASI — able to work across
web, mobile, tablet, desktop, and pod surfaces as a single continuous
workspace, riding the house Tailscale mesh between machines.

The pattern is slide-through control: work moves from surface to surface
without re-login, re-pairing, or losing context — the way a hand moves
across a desk.

## Compatibility

- Surfaces (target): house web apps, the Dell and Lenovo desktops, the
  house mobile and tablet seats, and the Ant 32 pod fleet.
- Transport: the house Tailscale mesh. No surface is exposed off-mesh.

## Safety

- Control is per-agent and attributable: every action rides one named
  agent's hand, and the mesh identity is that agent's own.
- Body gates stay with the owner — biometric, payment, ID, and legal
  signature steps are never carried by a control hand.
- Pods execute only brain-validated tasks, per standing pod law; a control
  hand reaching a pod does not change that.

## Supported operations

- Reserved pending the spec: cross-surface session continuity, unified
  pointer/keyboard routing between house desktops, and pod supervision
  from any surface.

*Implementation is house-original, built from a studied function pattern.
No third-party code or text is used.*
