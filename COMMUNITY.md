# Community Skills

The skill library is the heart of AntFlash 32, and it grows the same way the
catalog it mirrors grew: one well-written skill at a time, contributed by the
people who run the hardware.

A skill teaches the house agents — and any reader — how one board, pod, or
protocol is handled: what chips it fits, how it is set up, what is safe, and
what operations it supports.

## Add a skill

1. **Fork** this repository.
2. **Create your folder** under `skills/`, named in the house pattern:
   lowercase, hyphenated, descriptive — e.g. `skills/flash-esp32-s3/`.
3. **Write `SKILL.md`** inside it with these sections, in this order:
   - **Compatibility** — exact chips, boards, and revisions covered.
   - **Setup** — the steps, in order, from a bare board to ready.
   - **Safety** — what can go wrong, what never to do, recovery first.
   - **Supported operations** — what the skill can do once set up.
4. **Register it** in `skills/CATALOG.md`: add one line under the matching
   category, in the catalog's format — name, link, one-line summary of
   capability and limits.
5. **Open a pull request** against `main` with a short note on the hardware
   you tested against.

## House rules for contributions

- **Your own hardware, your own bench.** Skills cover devices the author
  owns and networks the author runs. Nothing that targets other people's
  systems is accepted — no exceptions, no "research purposes" carve-out.
- **Honest status.** If a step is untested, say so in the skill. A labeled
  stub beats a confident guess everywhere in this repo.
- **Licenses stay attached.** Firmware or code from an up<MASKED_USER_ID_001>eam project
  keeps its license text and attribution with it, per that project's terms.
- **One skill, one subject.** A board family, a pod, a protocol. If it needs
  two subjects, it is two skills and a catalog line each.
- **Original words.** Write the skill from your own bench notes. Do not copy
  another project's documentation text into a house skill.

## Review

Pull requests are reviewed for accuracy against real hardware, safety
section completeness, and catalog fit. A skill merges when a reviewer can
follow it top to bottom on the named hardware and end in the state it
promises.

Questions and proposals start as GitHub issues on this repo.
