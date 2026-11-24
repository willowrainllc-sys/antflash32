# Ant Wake Word Setup

Build the house wake-word detector from this repo checkout, verify it on your
own machine, and only then opt in to microphone use.

## Compatibility

- Hosts: the house Linux seats (rig, Dell, Lenovo) and any Linux machine that
  can build the native detector library from source.
- Languages at ship: English, Spanish, French, Portuguese — each language
  carries its own variant of the same wake call.
  - Spanish: **"Hola Antonio"** — confirmed by the owner.
  - English: OWNER-PICK-PENDING.
  - French: OWNER-PICK-PENDING.
  - Portuguese: OWNER-PICK-PENDING.
- A language whose variant is OWNER-PICK-PENDING ships with the slot present
  and the detector untrained for that phrase. Do not substitute a guessed
  phrase.

## Setup

1. Clone this repo and build the native detector library from the checkout —
   never from a prebuilt binary downloaded elsewhere.
2. Run the local verification pass: speak the wake call for each confirmed
   language at normal volume, at arm's length, and confirm the detector
   fires on the call and does not fire on ordinary conversation.
3. Review the verification log. Only after a clean pass, opt in to
   microphone use on that seat.
4. Record the seat, the languages verified, and the date in the seat's
   setup notes.

## Safety

- Microphone stays off until step 3 is complete. No exceptions for "just
  testing."
- Detection runs on the seat, locally. Audio is never <MASKED_USER_ID_001>eamed off the
  machine for wake-word detection.
- A false-positive rate above the verification threshold means the build
  does not ship to that seat — retrain or leave the seat on push-to-talk.

## Supported operations

- Wake the house assistant on the seat, hands-free, in any confirmed
  language.
- Per-seat opt-in and opt-out; opting out returns the seat to push-to-talk
  immediately.
