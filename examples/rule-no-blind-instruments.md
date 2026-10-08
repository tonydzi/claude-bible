---
title: "Rule — every instrument reports its own coverage as a number"
type: reglament
date_established: 2026-10-01
status: active
origin: owner
authored_by: agent
audience: both
---

# Rule — every instrument reports its own coverage as a number

> Established by the owner, 2026-10-01, after two checkers were caught printing
> confident verdicts about subjects they had barely looked at. Changed only by the owner.

## Why

A script that reports `0 problems` and a script that reports `0 problems, and I could only
examine 4% of the subject` look identical in a terminal, and only one of them is useful.
Agents build these checkers constantly — a gate, a watchdog, a "is everything fine" command —
and the failure is never a crash. It is a green line that answers a narrower question than
the one you asked.

Two measurements on the same day paid for this rule:

- A queue checker printed `proposals: 69 · UNMARKED=5 · pending=2 · NO-TARGET=61 · applied=1`.
  `NO-TARGET` looked like one category among several. It actually meant *"I have no idea
  about 88% of this queue"* — the verdict covered 4% of the subject, and the output said
  nothing about that.
- A freshness gate printed `fresh (need=0)` for a directory holding 12 local files against
  48,507 in the full set. The answer was correct for those 12 and silent about the rest:
  formally green, factually judging 0.02% of the thing it was named after.

Neither was a bug in the usual sense. Both passed their own tests.

## The rule

1. **Trigger:** any instrument that prints a verdict about a set — a linter, a gate, a
   health check, a watchdog, a "find all X" report.
2. **Action:** every report carries one line naming what it could *not* judge and why:
   `cannot judge N of M — reason`. Then define blind: an instrument is **blind** when
   coverage is under 90%, or when "don't know" outnumbers its verdicts. A blind instrument
   must say so in its own output, loudly, next to the verdict.
3. **Boundary:** this is about *reporting* coverage, not about achieving full coverage. A
   checker that honestly says it can only see 4% is doing its job; one that sees 4% and
   implies 100% is worse than no checker, because it converts an open question into a
   false answer. "Look at it yourself" does not count as a verdict.

Two numbers that must never be mixed: *what the instrument examined* and *what exists*.
The moment a report states only the first, the reader will assume it is the second.

## A useful corollary

Whoever builds the instrument owns its coverage — not just its correctness. "It works on the
files it reads" is not a defense if nothing told the reader which files those were.

## Related

- [Rule — objection sparring](rule-objection-sparring.md) — the same instinct applied to
  conversation: a verdict needs the argument against it stated out loud.
- `templates/rule-template.md` — the shape every rule in this framework follows.
