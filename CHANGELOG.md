# Changelog

All notable changes to Dropgap are recorded here.

Stage test results also go here, especially what the testers actually
said. See [README.md](README.md) and [PLAN.md](PLAN.md).

## [Unreleased]

### Added

- Stage 2a: a session of five rounds. Round counter and running total at
  the top; after the fifth round a session result with the total and one
  bar per round (length = bucket width, filled = caught, colour = dead
  centre or edge). `?seed=N` fixes all five rounds. Tapping the result
  starts a new session. No share button yet.
- Stage 1 prototype (`index.html`): one round, one page. A ball drops,
  bounces off three randomly tilted platforms, fades out after the first
  bounce. The player places a bucket (drag to move, drag up/down to
  narrow/widen, rim handles to resize); letting go plays the simulation,
  slowing slightly before the rim. Result: dead centre / edge / miss.
- Seeded rounds: `?seed=N` reproduces a round; the seed is shown top-left.
- `README.md` as the project entry point.
- `CHANGELOG.md` for changes and stage test results.

## Stage 1 — Mechanic test

- 2026-09-10: Stage 1 passed the live check. Waiting for the five-person test.
- 2026-09-10: Stage 1 passed the five-person test. Stage 2a opened.

Prototype built. Testing with five people.

**Stop test:** do five people say "one more"?

### Tester notes

_Record here what each of the five testers said after playing._
