# Changelog

All notable changes to Dropgap are recorded here.

Stage test results also go here, especially what the testers actually
said. See [README.md](README.md) and [PLAN.md](PLAN.md).

## [Unreleased]

### Changed

- Two more fade steps on the 1–2 segment: the ball can also be gone a
  quarter and three quarters of the way along it. Two platforms now
  have six fade steps (after the 2nd bounce, near the 2nd platform,
  three quarters, half, a quarter, right after the 1st bounce), three
  or more have eight (near the 3rd, halfway to it, after the 2nd,
  then the same five). The ceiling stays near the third platform. The
  quarter points are measured on the part of the hop that "right after
  the first bounce" does not already show (the bounce plus the 0.28 s
  fade), so every step is distinct and in order on every hop; the
  halfway step now follows the same rule. Rows last steps × 2 rounds:
  1–12, 13–28, 29–44, 45–60, 61–76, 77–92, 93–108, 109–124, 125–140,
  141–156, 157–172, 173–188, 189–204. The session is untouched.
- Bucket lock, both modes: while the ball can be seen, and while it
  fades, a touch does nothing. Once the ball is gone the bucket opens.
  Locked, the bucket is drawn faint; when it opens it returns to
  normal. No other sign. Watch first, then place.
- Endless ladder v3 (PLAN §2e.5), replacing the §2e.1 table. Two nested
  sawtooths: the world sets the platform count (2, 3, 4, 5), each world
  climbs through dash levels (full, light, dashed, more dashed, sparse
  dots), and each dash level walks the ball's fade-out from most seen
  to least: four steps with two platforms (after the second bounce, near
  the second platform, halfway, right after the first bounce), six with
  three or more (near the third platform, halfway to it, after the
  second bounce, then as before); the ceiling is the third platform.
  Two rounds per step; the checkpoint is the step. A new dash level
  restarts the fade; a new world adds a platform and returns the bars
  to full. The widest bucket goes ×1 → ×2 at world 3 and ×2 → ×3 at
  world 4's second level. Thirteen rows, 152 rounds; after the table
  the last step holds. Bar endpoints always stay. The platform strength
  lever and the endpoints-only drawing are gone from endless. One place
  (`ENDLESS_LADDER`), one row per (world, dash level); adding a world is
  adding rows. The session is untouched.
- Dashed trail (PLAN §2e.4, finding 3), endless only: once the ball is
  gone, the path the player saw stays as a faint dashed line while the
  bucket is placed, and disappears when the result plays. It shortens
  step by step down the ladder and comes back in full in a new world.
- The first bounce carries information again (PLAN §2e.4, finding 2).
  The ball's drop x now spans the whole width (40 to 360 instead of 110
  to 290), so the first platform sits anywhere across the field. The
  first platform's tilt runs from 5° to 22° instead of 6° to 18°, and
  one first platform in five is nearly flat (3° to 5°, aimed near its
  downhill end so the ball clears it coming down): the first bounce goes
  left, right, or nearly straight up. The other platforms, the no-wall
  and downhill-half rules, and the physics are unchanged. Session seeds
  change (accepted). Measured over 400 seeds with three platforms: left
  40%, straight (within 12° of vertical) 24%, right 37%; drop x 10th to
  90th percentile 81 to 317. Five-platform levels take a little longer
  to generate (about 60 ms, worst seen 234 attempts).
- Closed a rule gap in the endless checkpoint: a replayed round came
  back with the same trajectory, so the landing spot could be memorised
  and taken with the narrowest bucket. The round seed now comes from
  three things: the run seed, the round number, and how many times that
  round has been started. The first attempt is the plain seed, so a URL
  seed reproduces the same run; a round is never seen twice. The session
  is untouched.
- The mode word ("endless" in the session, "session" in endless) moves
  from the end card to the header, next to the seed, small, always
  visible in both modes; a tap switches to the other mode. With the
  band checkpoint an endless run has no end inside the game, so the
  run-end card is never reached and no longer needed; its code stays
  and is not called. The session end card is unchanged apart from the
  word leaving it.
- Endless band checkpoint (PLAN §2e.3). A miss no longer ends the run:
  it sends the run back to the first round of its ladder band (a miss
  at round 20 restarts at 19, the start of the 19–21 band). The rounds
  played since the band start and their points are gone; the highest
  total reached and the best stay, the run-end card and its "reached"
  text are unchanged. At the miss moment the round counter and the
  strip already show the band start. The run ends when the player
  leaves. The session is untouched: a miss still zeroes it and ends it.
- Fixed: in a long endless run the header strip stayed one slot to
  the right after round six (its slide animation never advanced), so
  the current round's slot was off the edge and the five bars were one
  round behind. Found while checking that the strip returns to the band
  start.
- Touch area: the whole screen (PLAN §7.1). A drag starts anywhere,
  relative as before. Letting go drops the ball once the finger has
  left the dead zone at least once. A touch that never moved drops with
  the bucket as it is in the bottom half, and does nothing in the top
  half. Every part of the screen controls the bucket; a stray touch
  while looking cannot end the round.
- Layout, from the first two-person test (PLAN §7.1), four changes, no
  mechanic, physics or seed touched. The post-round "tap for the next
  round" moves from the bottom line, which nobody saw, to mid-field
  above the bucket, semi-transparent. The session end and the run end
  are one centred card: the total, the bars under it, "tap anywhere" at
  the foot; no button. The header band doubles (34 → 68 units), the
  strip bars grow with it, the seed and round text are readable on a
  phone. The touch area is the bottom half, not the bottom quarter, and
  the top half never reacts to a touch: looking at the platforms cannot
  drop the ball.
- Gesture, third form: the handles are gone. The bottom band of the
  field (about a quarter) is the single touch area. Movement is
  relative to where the finger landed, the bucket never jumps to it:
  sideways moves it, up narrows it, down widens it, both at once, a
  6-unit dead zone on each axis. Handle drawing and hit-testing
  removed. First-round hint: "drag sideways to move, up to narrow".
- Bucket gesture fix (superseded above): touching between the two
  walls is always a body drag, however narrow the bucket. A handle is
  only the 16-unit strip just outside its wall.
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

- Endless difficulty ladder (PLAN §2e.1), replacing the single-axis
  `ENDLESS_PLATFORM_STYLE`: one table (`ENDLESS_LADDER`), one row per
  round band, five columns: platform count (2 to 5), where the ball
  fades out (just before the second platform, halfway along the path
  to it, or right after the first bounce; geometry, not seconds), the
  lowest bucket step still on the ladder (×1, then ×2, then ×3), the
  platform strength, and the drawing (bar or endpoints). Eleven rows,
  each changing one column from the previous one; the plan's last row
  changes two (strength and drawing). A step leaving the ladder is
  shown: the old widest bucket collapses into the new one with a small
  "×1 gone" label; a bucket below the floor snaps to the nearest open
  step. The generator now places 2 to 5 platforms; the session's
  three-platform layout and its seeds are unchanged, endless seeds
  differ. The first bounce stays fully visible; endpoints never
  disappear. Session and `DIFFICULTY` untouched.
- Endless ceiling lever (superseded by the ladder above): how the
  platforms are drawn changes with the round, in one table
  (`ENDLESS_PLATFORM_STYLE`). Rounds 1–5 as the difficulty table says;
  6–10 a full bar at 45%; 11–15 no bar, only the two endpoints as
  small dots at full strength; 16 and on the endpoints at 60%.
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
- 2026-09-10: the single-axis lever was too steep ("the bars went too
  early"). Replaced by the §2e.1 ladder: four axes, one change per
  band, thirty rounds.
- 2026-09-10: first two-person test of the layout: "I did not know
  what to do" moments. The words were not where the eyes were, the
  header was too small on a phone, and a touch while looking dropped
  the ball. Four layout changes; style unchanged.
- 2026-09-10: the §2e.1 ladder passed: deaths around rounds 3, 5, 15,
  20 and 30, no pile-up in one band, "could not catch it" rather than
  "could not see it". New finding: starting over from round one is
  boring. Band checkpoint added; the water-pouring model (miss = replay
  the same section) rejected. Test: five runs, is the boredom gone?

## Stage 1 — Mechanic test

- 2026-09-10: Stage 1 passed the live check. Waiting for the five-person test.
- 2026-09-10: Stage 1 passed the five-person test. Stage 2a opened.

Prototype built. Testing with five people.

**Stop test:** do five people say "one more"?

### Tester notes

_Record here what each of the five testers said after playing._
