# Changelog

All notable changes to Dropgap are recorded here.

Stage test results also go here, especially what the testers actually
said. See [README.md](README.md) and [PLAN.md](PLAN.md).

## [Unreleased]

### Changed

- The bank layer ("take ×N · finish") went unused in three tests: the
  five-round session (2c), endless (2e), and endless with a best score.
  Removed in both modes; the code stays behind the mode table. The
  bucket width already asks the same question. Endless now scores the
  highest total reached before the miss: the run end reads "reached
  ×48 · lost at round 12" ("new best" when the run set it), the best
  is the highest reached, and "best N" sits in the header during a run.
- 2c closed: the "take ×N · finish" target is removed from the
  five-round session. With the fifth round banking by itself, stopping
  early is almost never worth it, so the target went unused, and that
  was correct play. The session's risk comes from the rule, not the
  button: continue and miss, and the total is gone. That rule stays,
  round 1 included. The target returns in 2e as the core of endless
  mode.
- Ladder ratio 1.29 → 1.22 (2c finding: the ×1 bucket covered 65% of
  the field and never missed, so "take and finish" was never used).
  ×10 stays at 26; ×1 is now about 156 instead of 260. Seeds produce
  the same rounds; only the buckets are narrower.
- Stage 2a fix, after the session check failed (five rounds did not feel
  like one session): the finished rounds now build up as a strip of five
  slots in the header, one bar per round, length = bucket width, filled =
  caught. The number above the bucket at the result moment is the points
  earned ("+3"), not the bucket's step.

### Added

- Endless ceiling lever: how the platforms are drawn changes with the
  round, in one table (`ENDLESS_PLATFORM_STYLE`). Rounds 1–5 as the
  difficulty table says; 6–10 a full bar at 45%; 11–15 no bar, only
  the two endpoints as small dots at full strength; 16 and on the
  endpoints at 60%. The endpoints never disappear, so the angle can
  always be derived; the first bounce stays fully visible. Physics,
  seeds and the generator are untouched. Endless only.
- Endless best score, kept on the device in `localStorage` (2e
  finding: a banked total needs somewhere to go, or taking and losing
  feel the same). The target reads "take ×35 · best 41"; the run end
  reads "banked ×35 · best 41", or "new best ×48" when the run set it.
  Just the number, no advice. The session is untouched.
- Stage 2e: endless mode, a push-your-luck run. Entry without a menu: a
  small "endless" word on the session end screen, or `?mode=endless`;
  the five-round session stays the default. No round limit. After each
  round: tap to continue, or "take ×N · finish" at the bottom right to
  bank the total and end the run. A miss takes everything. Score is the
  banked total. Difficulty holds at the fifth row from round 6 on, on
  purpose. The header shows the round number and the running total; the
  strip shows the last five rounds, older ones slide off to the left.
  Run end: "banked ×N after R rounds" or "lost at round R"; a tap starts
  a new run with seed N+1. No leaderboard, no sharing, no best score.
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
- 2026-09-10: 2c finding: the wide bucket was a free continue, so the
  take-and-finish target went unused. Ladder ratio lowered to 1.22.
- 2026-09-10: 2c closed. The target stayed unused after the narrower
  ladder, and not using it was correct play: five rounds are too short
  for push-your-luck. Target removed, miss-ends-session rule kept.
  The plan's 2c diagnosis ("if they never stop, the risk does not
  hurt") was wrong: the risk hurt, stopping was just unprofitable.
  2e moved ahead of 2d.
- 2026-09-10: 2e opened.
- 2026-09-10: 2e finding: take-and-finish still unused, because a
  banked total had nowhere to go. Local best score added to endless.
- 2026-09-10: still unused with a best score. Bank layer removed in
  both modes after three tests; the width already asks the same
  question. Endless scores the highest total reached before the miss.
- 2026-09-10: 2e check 2, the ceiling: "all the same" after round ten,
  where 2b predicted it. Lever applied: platform legibility, endless
  only.

## Stage 1 — Mechanic test

- 2026-09-10: Stage 1 passed the live check. Waiting for the five-person test.
- 2026-09-10: Stage 1 passed the five-person test. Stage 2a opened.

Prototype built. Testing with five people.

**Stop test:** do five people say "one more"?

### Tester notes

_Record here what each of the five testers said after playing._
