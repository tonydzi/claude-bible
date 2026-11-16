# rules-as-files plugin

An instructions-only plugin with one skill, `rules-as-files`. It helps Claude keep
rules for you, your team and your AI agents as one markdown file per rule, with
only a short index line (trigger, essence, pointer) in `CLAUDE.md` or `AGENTS.md`.

## What the skill does

- **Intake:** routes a newly stated rule to its home, writes it from a template,
  adds the index line, links related rules and names what will invoke it.
- **Slimming:** proposes splitting full prose rules out of an always-loaded file,
  showing before and after on your own text.
- **Precedence:** resolves conflicting rules (explicit `supersedes`, then owner
  rules, then newer date) and marks the loser as superseded instead of deleting it.
- **Declined journal:** records what was rejected and why, so old ideas are not
  re-proposed as new.
- **Objections:** turns a "no-go" into a numbered list of objections you can rebut.

## Contents

- `skills/rules-as-files/SKILL.md`: the workflow.
- `skills/rules-as-files/SPEC.md`: the full specification.
- `skills/rules-as-files/templates/`: rule, decision memo and declined-decisions templates.

## Install

```text
/plugin marketplace add tonydzi/claude-bible
/plugin install rules-as-files@claude-bible
```

Then say a new rule in chat, or ask Claude to slim your `CLAUDE.md`.

## Privacy

The plugin contains only Markdown and JSON. It runs no programs, starts no
servers and collects or sends no data. See
[PRIVACY.md](https://github.com/tonydzi/claude-bible/blob/main/PRIVACY.md).

## License

MIT.
