---
title: "Rule — never fan out near-identical pull requests into one repository"
type: reglament
date_established: 2026-10-01
status: active
origin: owner
authored_by: agent
audience: both
---

# Rule — never fan out near-identical pull requests into one repository

> Established by the owner, 2026-10-01, after counting what a fan-out actually produced.
> Changed only by the owner.

## Why

We opened **nine** pull requests of one template — `feat(integrations): add support for
<vendor>` — into a single repository. **Eight were closed.** One is still open.

The expensive part was not the eight rejections. It was what the closing comment on one of
them contained: a link to the project's own documented procedure for adding a new
integration. The door had been there the whole time. We never walked through it, because we
had already fired the volley and had nothing left to ask with.

This is the shape of the mistake: a fan-out feels like N contributions and lands as **one
event** — a stranger mass-producing patches without reading how the project works. A
maintainer reads the second one as a copy of the first, and the ninth as noise. Volume
reads as carelessness, and carelessness is the one signal that closes a door you cannot
reopen with a better patch.

Agents are unusually good at generating this failure, because templating the tenth variant
costs nothing and asking a human question costs a turn.

## The rule

1. **Trigger:** two or more pull requests into the same repository that differ only by the
   **name of an entity** — a vendor, a provider, a language, a model, an integration, a
   driver.
2. **Action:** that is **one** fan-out, not N contributions. Allowed order:
   open **one**, wait for a human to merge it, then do the rest — and prefer putting the
   rest in a **single** follow-up PR. Before any of it, read how the project says to add
   this kind of thing; a documented procedure outranks your patch, and ignoring one is
   usually why the patch is closed.
3. **Boundary:** genuinely independent changes to the same repository are not a fan-out —
   a bug fix, a doc correction and a feature can travel separately. The test is whether a
   reviewer could tell your PRs apart without reading the entity name.

## What to do instead when you have ten variants

Ask in an issue which shape the maintainer wants, with one working example attached. One
question that lands beats nine patches that do not, and it leaves you a person to talk to
rather than a closed tab.

## Related

- [Rule — objection sparring](rule-objection-sparring.md) — the internal version: push back
  before acting, not after the volley.
- `templates/decision-memo-template.md` — for when the answer is "change the approach", not
  "send more".
