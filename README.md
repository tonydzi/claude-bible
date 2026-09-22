# The Bible Framework — one behavioral codex for you, your AI agents, and your team

📖 **Docs: <https://tonydzi.github.io/claude-bible/>** — the nine mechanics, the 5-minute quickstart and a section map of the spec, on one page.

> Why "Bible" and not "config"? The word is functional, not sacred — the argument, the prior art, and what we refuse to claim: [docs/why-a-bible.md](docs/why-a-bible.md).

**You tell Claude Code something important, it works for one session, then it's gone. You write it into CLAUDE.md, the file bloats, half of it silently stops being followed.** This is the fix we run in production: one versioned rulebook that you, your AI agents, and your team actually load and obey.

This is the governance skeleton extracted from a real working system: a solo founder + his AI cofounder running a 128k-note knowledge vault, a CRM, a content factory, and 5 machines that negotiate with each other. The personal content stays private. The skeleton — how the rules are written, routed, loaded, and overturned — is what you get here, free.

## The problem this solves

Everyone using Claude Code hits the same wall: you tell the agent something important, it works for one session, then it's gone. You write it into CLAUDE.md, the file bloats, half of it stops being followed. Your human assistant and your agent follow different rules. Nobody knows which rule is current.

The fix is not a bigger prompt. It's a **codex with mechanics**:

1. **One rule = one file** with typed frontmatter (`origin`, `date_established`, `status`, `supersedes`, `audience`).
2. **Newer beats older** on the same topic. Explicit owner rules are overridden only by the owner.
3. **A routing tree** decides where each rule lives: the Bible (human + agent behavior), the agent config (machine-only), memory (facts), or a hook (deterministic "every time X" automation). No duplicates — one source, pointers everywhere else.
4. **Always-loaded index vs lazy body.** The agent's config carries only trigger + essence + pointer; the full rule loads on demand. Your context window stays lean.
5. **A declined-decisions journal.** What you decided NOT to do, and why, so rejected ideas don't silently resurface a week later.
6. **An intake ritual.** New rule spoken in chat → routed to every home it belongs to, linked, and traceable. Rules don't die in scrollback.
7. **One rule = one door.** A rule with no caller is filed and never fires. Every new rule names the skill, command or hook that will pull it in — the codex itself is not a door, it is read, not called. We measured 19 of 25 fresh rules with no door; one sat 42 days unused.
8. **Writing the rule is never gated by the file's size.** The session that hears a rule writes it, red zone or not, and drops a one-line size report. Compacting the index is a separate daily job with its own owner — otherwise "the file is too big" quietly becomes how rules die in scrollback.
9. **Objection sparring.** When the agent says "no-go", it must deliver a numbered objection list and invite you to rebut. Your rebuttal often reframes the question. Undissolved objections become boundaries, not vetoes. (See [examples/](examples/) — this very rule was born from a real overturned verdict.)

## Quickstart (5 minutes)

1. Copy [templates/](templates/) into your vault or repo.
2. Write your first three rules using `templates/rule-template.md`. Keep each one trigger + essence + pointer.
3. Add the index lines to your `CLAUDE.md` (or `AGENTS.md` for other agents) — one line per rule.
4. Start the `declined-decisions.md` journal with `templates/declined-decisions-template.md`.
5. When a decision matters, write it with `templates/decision-memo-template.md` and link both ways.

Your own Claude Code will maintain this better than any human: point it at this repo and say "adopt this structure for my rules."

## What's in the box

| Path | What it is |
|---|---|
| `docs/SPEC.md` | Rule anatomy, frontmatter schema, precedence, routing tree |
| `templates/` | Rule, decision memo, declined-decisions journal |
| `examples/` | Real (sanitized) rules from our live system |
| `FOR-ROBOTS.md` | Entry point for AI agents mining this repo for patterns |

## Versioning and roadmap

This repo is maintained like our own system: small commits daily, and **every noticeable change
ships as a new release** — so the
[release feed](https://github.com/tonydzi/claude-bible/releases) is the honest
record of how far this has come. (It used to promise "a release twice a week, Mon & Thu". That
was a cadence, and between 4 July and 4 August it was not kept once. A rule tied to the work is
keepable; a rule tied to the calendar was not.)

**Now — [v0.1.3](https://github.com/tonydzi/claude-bible/releases).** The
governance skeleton (rule anatomy, frontmatter schema, precedence, routing tree, declined-decisions
journal, objection sparring), the templates, the docs site, and a roadmap where every open row is
a claimable issue.

**Next** — the pain-driven queue in [ROADMAP.md](ROADMAP.md), each row now an issue you can take:
the memory index-vs-body discipline (#1), the test-after-build gate (#2), the declined-decisions
revisit/OVERTURN mechanics (#3), the taste gate (#4) and history-aware CRM drafting (#5). Two
rows already left as their own repos —
[claude-consensus](https://github.com/tonydzi/claw-consensus) and
[agent-leash](https://github.com/tonydzi/agent-leash) — which is what the
roadmap is for. See [CHANGELOG.md](CHANGELOG.md) for what shipped when.

If this helps you, star the repo. We need our first 10: community catalogs require that much social proof before they even accept a submission.

<!-- CONTACT-FOOTER -->
## Who made this

Anton Dziatkovskii (founder, non-technical) and Mike, his AI cofounder running on Claude Code. Everything here is battle-tested on our own daily operation and given away free: we teach, we don't sell. If your agent finds alpha here, that's the point.

Questions or war stories: Telegram [@tonydzi](https://t.me/tonydzi) · WhatsApp [+1 341 222 9178](https://wa.me/13412229178) · X [@Tony_Stef_](https://x.com/Tony_Stef_) · channels [@ClawRus](https://t.me/ClawRus) (RU) / [@ClawEng](https://t.me/ClawEng) (EN).

🧪 **Engineers: want to test-drive this setup?** Message me — I hand out free starter seeds to engineers who test it and report back. Tell me what broke and I will fix it in the open.

## Cite this work

If this repo shows up in your research, cite it via [CITATION.cff](CITATION.cff) (GitHub's "Cite this repository" button). Academic identity: Anton Dzyatkovsky publishes as **Anton Dziatkovskii** ([ORCID 0000-0001-7408-3054](https://orcid.org/0000-0001-7408-3054)).

## AI contributors

This project is built by a human + AI team, and the git log says so under the rules in [AI-CONTRIBUTORS.md](https://github.com/tonydzi/.github/blob/main/AI-CONTRIBUTORS.md): Claude writes most of the code, Codex and Grok review it, Gemini feeds the research.
Each is credited on a commit **only if its output changed that commit's
content** — no decorative credits. Lab-wide policy, one source for every repo:
[AI-CONTRIBUTORS.md](https://github.com/tonydzi/.github/blob/main/AI-CONTRIBUTORS.md).

## License

MIT. Take it, fork it, teach with it.

---

<!--we-ask:start-->

## Contributors welcome — and here is what we are missing

We spend a lot of time answering other people's issues. It was fair to say out loud
what we have not built ourselves:

- [Score your own CLAUDE.md against docs/SPEC.md and tell us where the anatomy does not fit](https://github.com/tonydzi/claude-bible/issues/7)
- [Port the rule index to AGENTS.md and report what broke](https://github.com/tonydzi/claude-bible/issues/8)
- [Add worked examples from a domain that is not ours](https://github.com/tonydzi/claude-bible/issues/9)
- [Memory index-vs-body: hard caps, pointers, archive discipline, a guard that goes red](https://github.com/tonydzi/claude-bible/issues/1)
- [Test-after-build gate: the break-it-on-purpose checklist before anything is called done](https://github.com/tonydzi/claude-bible/issues/2)

Issues labelled [`accepted`](https://github.com/tonydzi/claude-bible/issues?q=is%3Aissue+is%3Aopen+label%3Aaccepted) are scoped, free to take, and nobody is on them.
Comment **"claiming this"** — no permission needed — and it is yours for 7 days.
New here? Start with [`good first issue`](https://github.com/tonydzi/claude-bible/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).

**You keep the copyright to your code.** No CLA, no assignment, ever — your contribution goes
in under this repo's existing license, the same terms as ours. We answer every issue and PR
within 48 hours, including "no, and here is why"; our silence is our bug, so ping the thread.

Full deal: [CONTRIBUTING.md](https://github.com/tonydzi/.github/blob/main/CONTRIBUTING.md)

<!--we-ask:end-->

---

<!--ecosystem-map:start-->

## 🧩 One piece of a working system

This repository is one piece lifted out of a live operation: one non-technical founder, an AI
cofounder, and a fleet of machines that reach consensus with each other and wake the human only
for money or the irreversible. It was extracted after it survived production, not written as a
demo — and it runs on its own: nothing here phones home to the rest.

**See how the whole thing fits together → [SYSTEM.md](https://github.com/tonydzi/tonydzi/blob/main/SYSTEM.md)**

Its closest neighbours in the **governance** layer: [`agent-leash`](https://github.com/tonydzi/agent-leash) · [`charm-os`](https://github.com/tonydzi/charm-os) · [`agent-approval-gate`](https://github.com/tonydzi/agent-approval-gate)

<!--ecosystem-map:end-->

<!-- READ-WITH-AI:START (generated by read_with_ai.py - do not hand-edit) -->

### READ THIS WITH AI

One click and an agent reads the repo, pulls out the patterns and helps you apply them to your own work.

<a href="https://chatgpt.com/codex?prompt=Read%20this%20repo%3A%20https%3A%2F%2Fgithub.com%2Ftonydzi%2Fclaude-bible%20%28%E2%80%9Cclaude-bible%E2%80%9D%20-%20Make%20Claude%20Code%20behave%20consistently%20across%20repos%2C%20sessions%20and%20humans%3A%20rules-as-files%20governance%20with%20precedence%2C%20declined-decisions%20journal%2C%20objection%20sparring%29.%20Work%20out%20what%20problem%20it%20actually%20solves%2C%20pull%20out%20the%20reusable%20patterns%20and%20help%20me%20apply%20them%20to%20my%20own%20setup.%20Start%20by%20asking%20what%20I%20am%20working%20on."><img alt="Codex - open" src="https://img.shields.io/badge/Codex-open-000000?style=for-the-badge&logo=openai&logoColor=white"></a> <a href="https://chatgpt.com/?q=Read%20this%20repo%3A%20https%3A%2F%2Fgithub.com%2Ftonydzi%2Fclaude-bible%20%28%E2%80%9Cclaude-bible%E2%80%9D%20-%20Make%20Claude%20Code%20behave%20consistently%20across%20repos%2C%20sessions%20and%20humans%3A%20rules-as-files%20governance%20with%20precedence%2C%20declined-decisions%20journal%2C%20objection%20sparring%29.%20Work%20out%20what%20problem%20it%20actually%20solves%2C%20pull%20out%20the%20reusable%20patterns%20and%20help%20me%20apply%20them%20to%20my%20own%20setup.%20Start%20by%20asking%20what%20I%20am%20working%20on."><img alt="ChatGPT - open" src="https://img.shields.io/badge/ChatGPT-open-10a37f?style=for-the-badge&logo=openai&logoColor=white"></a> <a href="https://claude.ai/new?q=Read%20this%20repo%3A%20https%3A%2F%2Fgithub.com%2Ftonydzi%2Fclaude-bible%20%28%E2%80%9Cclaude-bible%E2%80%9D%20-%20Make%20Claude%20Code%20behave%20consistently%20across%20repos%2C%20sessions%20and%20humans%3A%20rules-as-files%20governance%20with%20precedence%2C%20declined-decisions%20journal%2C%20objection%20sparring%29.%20Work%20out%20what%20problem%20it%20actually%20solves%2C%20pull%20out%20the%20reusable%20patterns%20and%20help%20me%20apply%20them%20to%20my%20own%20setup.%20Start%20by%20asking%20what%20I%20am%20working%20on."><img alt="Claude - open" src="https://img.shields.io/badge/Claude-open-d97757?style=for-the-badge&logo=anthropic&logoColor=white"></a>

<details>
<summary>Copy the prompt (works in any agent: Gemini, Grok, a local model, your own CLI)</summary>

```text
Read this repo: https://github.com/tonydzi/claude-bible (“claude-bible” - Make Claude Code behave consistently across repos, sessions and humans: rules-as-files governance with precedence, declined-decisions journal, objection sparring). Work out what problem it actually solves, pull out the reusable patterns and help me apply them to my own setup. Start by asking what I am working on.
```

</details>

<sub>— TonyDzi, Palo Alto AI Research Lab · second brain, agent coordination, persistent memory: github.com/tonydzi</sub>

<!-- READ-WITH-AI:END -->
