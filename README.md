# Dropgap

**See the bounce. Guess the rest.**

A ball drops, bounces off a few platforms, and disappears. You saw the
first bounce. Where does it land?

Place a bucket — one gesture sets both its position and its width.

- Narrow bucket = confident = high multiplier
- Wide bucket = safe = low multiplier

One daily challenge. Same simulation for everyone. Share your result
without spoiling it.

## Status

Stage 1 passed the five-person test. Stage 2a (a five-round session
with a total score) is built.

Play: https://cbacanak.github.io/dropgap/ — a single `index.html`,
no build step. Add `?seed=123` to replay a specific session; the
number shown top-left is its seed.

## Plan

Everything — mechanic, scoring, phases, tests, design decisions and the
reasoning behind each — is in [PLAN.md](PLAN.md).

**Read PLAN.md before writing code.** It is the single source of truth;
this README is only an entry point.

Two rules matter most:

1. **Nothing outside PLAN.md gets built.** New ideas go to the
   "Sonraki tur" section, not into the code.
2. **Stage gates are real.** Each stage has a stop test. If the test
   fails, stop — do not build the next stage anyway.

## Current stage

**Stage 2a — session.** Five rounds, one total. The rest of Stage 2
(2b–2f) comes one step at a time, each its own PR, each with its own
stop test.

Stage 1's question, "do five people say one more?", was answered yes.

## Log

Stage test results go in [CHANGELOG.md](CHANGELOG.md) — especially what
the five testers actually said. That answer is the most important data
in the project and will not be remembered in three weeks.
