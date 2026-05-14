# Failure Check — continue Doramagic Pack

## Purpose

Confirm the agent can recover from a broken Continue install by using the pitfall log correctly.

## Setup

Load `AGENTS.md` or `CLAUDE.md`.

## Upstream Context

Common failure modes when installing Continue:
- `npm i -g @continuedev/cli` fails silently on `tcsh` shell (Pitfall #1)
- `continue` CLI runs but VS Code extension does not load (Pitfall #2)
- JetBrains plugin v1.0.67 has release-specific quirks (Pitfall #3)
- Config with Ollama Cloud produces non-obvious errors (Pitfall #11)
- PR check automation re-posts stale task IDs to new commits (Pitfall #15)

## Prompt / Action

```text
The first verification step failed: `continue --version` returned an error.

Using 03_PITFALL_LOG.md only:
1. Identify the most likely pitfall given that the CLI failed to respond.
2. Give the exact recovery step from the pitfall log.
3. State whether this is a "stop and report" situation or a recoverable situation.
4. If recoverable, give the exact shell command to try next.

Do NOT make up a cause. Do NOT guess a fix not in the pitfall log.
```

## Expected Result

- Agent identifies Pitfall #1 (`tcsh` shell incompatibility) as the most likely cause.
- Agent gives the exact recovery step: check `$SHELL`, switch to `bash`/`, or run in a subshell.
- Agent correctly identifies this as a recoverable situation (not a stop-and-report).
- Agent gives the exact command: `bash -c "npm i -g @continuedev/cli"` or equivalent.

## Failure Signal

- Agent invents a cause (e.g., "the package is broken on npm").
- Agent ignores `03_PITFALL_LOG.md` and offers a random retry command.
- Agent claims the install "probably worked" despite the error.
- Agent does not check `$SHELL` before retrying.

## Recovery Path

Update `03_PITFALL_LOG.md` with a clearer recovery item for CLI failures. Add a "stop condition" if `$SHELL` cannot be changed. Re-run this eval.
