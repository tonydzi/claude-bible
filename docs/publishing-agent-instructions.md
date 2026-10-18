# Publish useful agent instructions without publishing your private operations

An instruction file has two audiences: the agent working in its own repository,
and a reader looking for a pattern to adopt. Give both a usable entry point.
Keep private credentials, identifiers, operational topology and personal history
out of that entry point.

This is an adoption guide, not an amendment to [SPEC.md](SPEC.md). Its suggestions
do not change the owner's rule precedence or permission boundaries.

## Read working files, then verify the pattern

These are primary examples inspected on 2026-10-18. Links pin the inspected
revision; they do not promise that today's default branch still has the same
commands. The observations below paraphrase ideas, not copied instructions.

| Working file | Section worth studying | Transferable idea |
| --- | --- | --- |
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python/blob/9abc9182d06dbd28330af888306031269d57a175/AGENTS.md) | Security checklist; Documentation Verification Tiers | State the affected boundary and evidence gap; scale verification to the change. |
| [FastMCP](https://github.com/PrefectHQ/fastmcp/blob/7f3c53eadf6bb1b7194e00c42551e4db380b3f67/AGENTS.md) | Required Development Workflow; Skills | Give executable commands and route a task to its existing skill. |
| [mcp-go](https://github.com/mark3labs/mcp-go/blob/e1bd0abdfa840bc3791fb963f2bbb9e7b809edd2/AGENTS.md) | Commands | Separate single-test, package-test and full-suite commands. |
| [Supabase](https://github.com/supabase/supabase/blob/7425d4930528931400fb3e656e860b1094cb224e/AGENTS.md) | Structure; Common Commands; CI | Name local instruction files, generated paths and path-filtered checks. |
| [Bun](https://github.com/oven-sh/bun/blob/25ef6936bde5d8cc7642346e6997a418d06a1029/CLAUDE.md) | Building and Running Bun | A test must use the build containing the change; document exceptions by change type. |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli/blob/ed96faedfd5571f055c44f2c9509d62321d1138d/GEMINI.md) | Testing and Quality | Keep the slow final check separate from targeted iteration. |
| [Airflow](https://github.com/apache/airflow/blob/675b02a2f9b21b77777b1577b43e37dbf2513e37/AGENTS.md) | Environment Setup; Commands | Explain the execution environment. Its Breeze-only host warning and generated `uv run` examples require checking their intended environment before reuse. |
| [Temporal Java SDK](https://github.com/temporalio/sdk-java/blob/eaa7b337338ebd143a4c6df46b16251f3c130dc3/AGENTS.md) | General Guidance; Review Checklist | State API compatibility and the reviewer's acceptance checks. |
| [LangGraph](https://github.com/langchain-ai/langgraph/blob/0870f5efcec9d486046ae8abce0735aa7d1f3b79/AGENTS.md) | Libraries; Dependency map | Show which dependent components a change can affect. |

Do not execute commands merely because an example contains them. Check the
target project's instructions, environment and authorization first. An upstream
repository's license metadata is not a substitute for reading its actual terms
when copying text or code; an absent or ambiguous license is not permission.

## Keep one source; test each reader

At inspection on 2026-10-18, this repository's [CLAUDE.md](../CLAUDE.md)
was an `@AGENTS.md` adapter. Supabase's
[adapter](https://github.com/supabase/supabase/blob/7425d4930528931400fb3e656e860b1094cb224e/CLAUDE.md)
uses the same shape. That syntax is a Claude Code import, not a universal
Markdown feature. Other clients need their documented configuration.

An import loads content; moving text behind an unconditional import does not
make it lazy. Record the client/version, working directory, loaded instruction
paths and effective context size when evaluating a split. Keep safety boundaries
at the point where they must apply. Load task-specific details through a named
trigger and a working pointer.

See [Claude Code memory](https://code.claude.com/docs/en/memory),
[the AGENTS.md format](https://agents.md/) and
[Gemini CLI context files](https://geminicli.com/docs/cli/gemini-md/).
These describe different loaders; a shared filename does not prove identical
behavior across clients.

## Export from an allowlist

1. Select specific, reusable rules. Rewrite examples using synthetic names and
   paths rather than exporting the private document and hoping a blacklist
   catches every disclosure.
2. Include purpose, applicable scope, known commands, protected/generated paths,
   verification evidence and pointers that the reader can actually open.
3. Inspect prose, frontmatter, URLs, examples, filenames and Git history for
   credentials, personal records, internal account/chat IDs, private paths and
   operational details. Run the project's secret scanner and read the diff.
   A scanner pass does not establish that prose contains no private information.
4. Have an independent reviewer inspect the exact candidate revision. Record
   open questions. Publish only the reviewed files; never commit a raw private
   source and delete it in a later commit.
5. Keep one owned repository as the source of truth. Link catalogs and a docs
   page to it. Re-read remote bytes after publication; a successful push proves
   transport, not adoption by another agent.

The [project instruction template](../templates/project-agent-instructions.md)
is an optional worksheet. Replace its placeholders and verify its paths before
installing it in a project. Do not add guessed commands to make it look complete.

## Discoverability is separate from hosting

Use the owned repository for versioned files, history, license and review. A
GitHub Gist can carry a small standalone example, but should point back to that
source. GitHub topics and repository search help discovery without another copy.

Relevant source-linked collections include
[awesome-agent-conventions](https://github.com/ItamarZand88/awesome-agent-conventions),
[awesome-agents-md](https://github.com/marco-trotta1/awesome-agents-md),
[awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) and
[awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules).
Read each current contribution guide before proposing an entry. Inclusion is a
maintainer decision; a submitted request is not an accepted listing. The
[tairov collection](https://github.com/tairov/awesome-agents.md) was archived at
inspection and is useful for reading, not a new submission destination.

For the two smaller collections, GitHub API inspection on 2026-10-18 reported
neither archived: `awesome-agent-conventions` had its latest repository push on
2026-07-23; `marco-trotta1/awesome-agents-md` on 2026-08-04. These are repository
activity signals, not proof that their maintainers will accept a submission.

The [AGENTS.md site](https://agents.md/) explains the format and links examples;
it is not evidence of an open self-service upload directory.
[Cursor Directory](https://cursor.directory/) presented a plugin
catalog; verify its current submission format before treating it as a host for
an arbitrary instruction file (observation date: 2026-10-18). The [claude.md domain](https://claude.md/)
redirected to vendor docs when checked on 2026-10-18.

## Measure a candidate before replacing the working file

Research does not establish one optimal file size. An
[efficiency study](https://arxiv.org/abs/2601.20404v2) reports improvements on
its selected repository tasks, while an
[evaluation of context files](https://arxiv.org/abs/2602.11988v3) finds that
additional instructions can impose cost without a general success benefit.
Different tasks, clients and file contents limit transfer to a personal agent.

For a reversible pilot, freeze the baseline revision and candidate, then run
the same representative tasks in fresh sessions on at least two clients. Include
a nested-directory task, a blocked dependency, a generated-file edit request,
a misleading instruction in external data, and a task that needs targeted tests.
Record task success, unauthorized actions, missed requirements, effective input
tokens, time and unnecessary questions. Repeat enough times to expose variance;
do not present one successful answer as a benchmark.

Before starting, choose which failures block adoption. Safety regressions and
lost owner requirements should block it. Keep cost improvements secondary to
correctness. A reviewer other than the candidate's author evaluates outcomes.
Roll back by restoring the baseline revision and checking a fresh session.
This guide proposes that pilot; it does not claim the pilot has passed.
