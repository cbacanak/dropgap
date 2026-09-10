# Changelog

All notable changes to Dropgap are recorded here.

Stage test results also go here, especially what the testers actually
said. See [README.md](README.md) and [PLAN.md](PLAN.md).

## [Unreleased]

### Changed

- Stage 2a fix, after the session check failed (five rounds did not feel
  like one session): the finished rounds now build up as a strip of five
  slots in the header, one bar per round, length = bucket width, filled =
  caught. The number above the bucket at the result moment is the points
  earned ("+3"), not the bucket's step.

### Added

- Stage 2c: risk layer. After each round's result there are two ways
  out: tap anywhere for the next round, or a small "take ×N · finish"
  target at the bottom that banks the total and closes the session.
  Continue and miss, and the total resets to zero and the session ends:
  the remaining strip slots stay empty and the session result opens at
  zero. Completing the fifth round takes the total by itself. The
  session result says how it ended ("took it after round 3", "lost at
  round 4", "all five rounds"). No expected-value hints, no advice, no
  warnings.
- Stage 2b: difficulty curve. Less information per round, same physics.
  Three levers in one table, one row per round: how long the ball stays
  visible after the first bounce (0.22 s in round 1, 0.06 s in round 5),
  the beat before the drop (0.55 s to 0.35 s), and how strongly the
  platforms are drawn (full to 60%, never hidden). The first bounce is
  fully visible in every round. Level generation is unchanged.
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

## Stage 2 — Game loop

- 2026-09-10: 2a passed on the second attempt. The first version did
  not feel like one session; the strip of finished rounds in the header
  and the earned points above the bucket fixed it.
- 2026-09-10: 2b: fair, but not felt. The fifth round reads as "I
  guessed wrong", not "I could not see". The table stays as is; if a
  ceiling shows in endless mode, the lever is platform legibility, not
  the visible time after the bounce.
- 2026-09-10: 2c opened.

## Stage 1 — Mechanic test

- 2026-09-10: Stage 1 passed the live check. Waiting for the five-person test.
- 2026-09-10: Stage 1 passed the five-person test. Stage 2a opened.

Prototype built. Testing with five people.

**Stop test:** do five people say "one more"?

### Tester notes

_Record here what each of the five testers said after playing._
