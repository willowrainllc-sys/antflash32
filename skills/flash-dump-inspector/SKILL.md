# Flash Dump Inspector

Read-only inspection of a board's flash against the package it is supposed
to be running.

## Compatibility

- Any ESP32-family board the flasher can connect to.
- Inputs: a connected board, or a dump file captured from your own board.

## Supported operations

- **Read back** — dump the connected board's flash to a local file.
- **Compare** — diff a dump against the manifest's parts for the claimed
  package: matching regions, missing regions, unexpected content.
- **Report** — a plain verdict: matches the manifest, differs (with the
  regions named), or unreadable (with the reason).

## Safety

- This skill **never writes**. There is no erase, no patch, no "fix it for
  me" path — a mismatch is fixed by re-flashing under the proper chip
  skill, not here.
- Dumps can contain the board's credentials and keys. Treat a dump like a
  password file: local storage only, never committed to this repo, never
  shared.

## Setup

1. Connect the board over Web Serial (or open an existing dump file).
2. Pick the manifest the board claims to run.
3. Run the compare and read the verdict.
