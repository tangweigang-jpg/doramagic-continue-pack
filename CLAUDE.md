# CLAUDE.md — continue Doramagic Pack

This file augments `AGENTS.md` with Claude Code-specific runtime behavior. Load `AGENTS.md` first.

---

## Runtime Instructions

### Before Any Tool Call

1. Read `00_QUICK_START.md` to understand the two-minute path.
2. Confirm the user wants Continue loaded as a source-controlled coding-agent workflow.
3. Identify whether your next action requires: external tools, browser, network, filesystem, or credentials.
4. If the action is risky, state it and wait for approval before proceeding.

### Installing Continue

Do NOT run `npm i -g @continuedev/cli` without checking `03_PITFALL_LOG.md` first.

Known blockers before install:
- **Pitfall #1**: `tcsh` shell causes hardcoded `-l` flag failures on Linux/macOS. Check `$SHELL` before installing.
- **Pitfall #2**: VS Code extension silently fails on certain Windows shell configs.
- **Pitfall #3**: JetBrains plugin v1.0.67 has release-specific quirks.

### Verifying the Install

Before claiming Continue is working:

1. Open `06_EVALS/smoke_check.md` and mentally run the prompt:
   - Does the agent restate the task correctly?
   - Does the agent propose a concrete verification step?
   - Does the agent avoid claiming success without evidence?
2. If the smoke check fails, open `03_PITFALL_LOG.md` — the top 3 pitfalls are listed at the top with actionable recovery steps.
3. Only claim the install is working after a real verification step passes.

### Boundary Enforcement

Before using any of the following, wait for explicit user approval:

| Action | Required Approval |
|--------|-------------------|
| `npm install`, `pip install`, or any package manager | Yes |
| Reading files outside the current project | Yes |
| Accessing credentials, API keys, or env vars | Yes |
| Network requests to non-public URLs | Yes |
| Browser automation or web scraping | Yes |
| Publishing, deleting, or modifying external systems | Yes |

### Recovery If Blocked

If you cannot proceed because a tool is missing, a command fails, or the smoke check fails:

1. Open `03_PITFALL_LOG.md`
2. Find the matching pitfall
3. Follow the recovery step exactly
4. Report back with:
   - What failed
   - What the recovery step was
   - Whether it succeeded
   - If it did not succeed — what the suspected cause is

If the failure is not in the pitfall log, write it to `TEST_LOG.md` and report it to the user.

### What NOT To Do

- Do not say "Continue is installed" or "Continue is working" without running a verification step
- Do not access secrets, credentials, or private data without explicit approval
- Do not modify `.continue/config`, `continue.rc`, or any Continue config file without user approval
- Do not imply this pack is affiliated with or endorsed by continuedev/continue
- Do not run `npx @continuedev/cli` in a production environment without sandboxing

---

## Tool Usage Reminder

- Use `Bash` with explicit flags — do not assume shell compatibility (see Pitfall #1)
- Check `$SHELL` before running any shell command that may use `-l`
- Prefer read-only operations until the smoke check passes
- Log all external tool invocations in `TEST_LOG.md` for traceability
