# 03_PITFALL_LOG.md — continue Doramagic Pack

## Top 3 Actionable Pitfalls

These are the most likely to block a fresh install. Check here first.

---

### Pitfall 1 (HIGH) — `tcsh` shell breaks `continue` terminal commands

**Symptom**: `npm i -g @continuedev/cli` or `continue` CLI commands silently fail or produce shell errors involving a `-l` flag.

**Likely cause**: The CLI uses a hardcoded `-l` flag for shell initialization, which fails when `$SHELL` is set to `tcsh`.

**Recovery**:
1. Run `echo $SHELL` — if it shows `/bin/tcsh` or `/usr/bin/tcsh`, this is the cause.
2. Temporarily switch to `bash` or `zsh` for the install: `SHELL=/bin/bash npm i -g @continuedev/cli`
3. Or: run the command in a subshell: `bash -c "npm i -g @continuedev/cli"`

**When to stop**: If switching shells is not allowed in your environment, do not proceed — the CLI will not function.

**Source**: [GitHub issue #12378](https://github.com/continuedev/continue/issues/12378) (open, unverified on current version)

---

### Pitfall 2 (MEDIUM) — VS Code extension silently fails to load

**Symptom**: The Continue extension is installed but does not appear in the VS Code activity bar.

**Likely cause**: Combination of VS Code version, platform (Windows), and shell config. May also affect JetBrains plugin variants.

**Recovery**:
1. Check VS Code version: `code --version` — ensure it is the latest stable.
2. Check the extension log: `code --verbose` and look for Continue-related errors.
3. Try a clean reload: `code --disable-extensions` then re-enable Continue.
4. If on Windows, verify no corporate AV or group policy is blocking extension initialization.

**When to stop**: If the extension loads in a clean VS Code profile (`code --profile default`) but not in the current profile, the issue is profile-level — not the extension itself.

**Source**: [GitHub issue #1312](https://github.com/continuedev/continue/issues/1312) (may be partially resolved)

---

### Pitfall 3 (MEDIUM) — JetBrains plugin release-specific quirks

**Symptom**: The JetBrains plugin installs but shows no tool window, or crashes on first use.

**Likely cause**: Specific releases (v1.0.67-jetbrains, v1.2.22-vscode, v1.3.38-vscode) have release-specific behavior that differs from the latest tag.

**Recovery**:
1. Check the installed version: look in JetBrains Settings → Plugins → Installed.
2. Cross-reference with known problematic releases: v1.0.67, v1.2.22, v1.3.38.
3. If on a problematic release, downgrade to the nearest stable release or wait for a patch.
4. Check the [releases page](https://github.com/continuedev/continue/releases) for changelog notes.

**When to stop**: If a release-specific bug is confirmed and no downgrade path exists, do not proceed — file a bug report instead.

**Source**: [Release v1.0.67-jetbrains](https://github.com/continuedev/continue/releases/tag/v1.0.67-jetbrains), [v1.2.22-vscode](https://github.com/continuedev/continue/releases/tag/v1.2.22-vscode), [v1.3.38-vscode](https://github.com/continuedev/continue/releases/tag/v1.3.38-vscode)

---

## Full Pitfall Index

| # | Category | Title | Severity | Source |
|---|----------|-------|----------|--------|
| 1 | Install | `tcsh` shell breaks terminal commands | HIGH | [#12378](https://github.com/continuedev/continue/issues/12378) |
| 2 | Install | VS Code extension silently fails to load | MEDIUM | [#1312](https://github.com/continuedev/continue/issues/1312) |
| 3 | Config | JetBrains plugin release-specific quirks | MEDIUM | [v1.0.67-jetbrains](https://github.com/continuedev/continue/releases/tag/v1.0.67-jetbrains) |
| 4 | Config | v1.2.22-vscode release notes | MEDIUM | [v1.2.22-vscode](https://github.com/continuedev/continue/releases/tag/v1.2.22-vscode) |
| 5 | Config | v1.3.38-vscode release notes | MEDIUM | [v1.3.38-vscode](https://github.com/continuedev/continue/releases/tag/v1.3.38-vscode) |
| 6 | Capability | Capability assumptions not verified | MEDIUM | [repo README](https://github.com/continuedev/continue) |
| 7 | Maintenance | Maintenance activity signals unknown | MEDIUM | [repo](https://github.com/continuedev/continue) |
| 8 | Security | Downstream validation risk: no demo | MEDIUM | [repo](https://github.com/continuedev/continue) |
| 9 | Security | No sandbox install executed yet | MEDIUM | [repo](https://github.com/continuedev/continue) |
| 10 | Security | Scoring risk: no demo | MEDIUM | [repo](https://github.com/continuedev/continue) |
| 11 | Security | Config error with Ollama Cloud | MEDIUM | [#12370](https://github.com/continuedev/continue/issues/12370) |
| 12 | Security | Undocumented `.continue/configs` directory support | MEDIUM | [#12377](https://github.com/continuedev/continue/issues/12377) |
| 13 | Security | Undocumented dynamic model fetching | MEDIUM | [#12376](https://github.com/continuedev/continue/issues/12376) |
| 14 | Security | Undocumented Mercury-2 model Inception provider | MEDIUM | [#12375](https://github.com/continuedev/continue/issues/12375) |
| 15 | Security | PR checks re-post stale task IDs to new commits | MEDIUM | [#12382](https://github.com/continuedev/continue/issues/12382) |
| 16 | Security | v1.2.19-vscode API key conditions | MEDIUM | [v1.2.19-vscode](https://github.com/continuedev/continue/releases/tag/v1.2.19-vscode) |
| 17 | Security | v1.2.20-vscode blocking issue | MEDIUM | [v1.2.20-vscode](https://github.com/continuedev/continue/releases/tag/v1.2.20-vscode) |
| 18 | Security | v1.3.35-vscode API key conditions | MEDIUM | [v1.3.35-vscode](https://github.com/continuedev/continue/releases/tag/v1.3.35-vscode) |
| 19 | Security | v1.3.36-vscode blocking issue | MEDIUM | [v1.3.36-vscode](https://github.com/continuedev/continue/releases/tag/v1.3.36-vscode) |
| 20 | Maintenance | issue/PR response quality unknown | LOW | [repo](https://github.com/continuedev/continue) |
| 21 | Maintenance | Release cadence unclear | LOW | [repo](https://github.com/continuedev/continue) |

---

## Pitfall Detail Entries (Sorted by Priority)

### Install Pitfalls

**P1 — `tcsh` shell breaks terminal commands** (see Top 3 above)

**P2 — VS Code extension silently fails to load** (see Top 3 above)

**P3 — JetBrains plugin release-specific quirks** (see Top 3 above)

---

### Config Pitfalls

**P4 — v1.2.22-vscode release notes**

- Severity: medium
- Source: [v1.2.22-vscode release](https://github.com/continuedev/continue/releases/tag/v1.2.22-vscode)
- Notes: Check release notes before installing this specific version. Some install paths may have changed.

**P5 — v1.3.38-vscode release notes**

- Severity: medium
- Source: [v1.3.38-vscode release](https://github.com/continuedev/continue/releases/tag/v1.3.38-vscode)
- Notes: Release-specific behavior may affect fresh installs. Verify against latest tag.

---

### Capability Pitfalls

**P6 — Capability assumptions not verified**

- Severity: medium
- Source: [repo README](https://github.com/continuedev/continue)
- Notes: README may claim capabilities that require live verification. Do not treat documentation as proof of functionality.

---

### Maintenance Pitfalls

**P7 — Maintenance activity signals unknown**

- Severity: medium
- Source: [repo](https://github.com/continuedev/continue)
- Notes: No structured last_activity signal found. Verify recent commits, issues, and PRs before trusting long-term support assumptions.

**P20 — issue/PR response quality unknown**

- Severity: low
- Source: [repo](https://github.com/continuedev/continue)
- Notes: Sampling recent issues and PRs is recommended before assuming community support quality.

**P21 — Release cadence unclear**

- Severity: low
- Source: [repo](https://github.com/continuedev/continue)
- Notes: Verify the most recent release date and tag against the README install command to avoid drift.

---

### Security / Permission Pitfalls

**P8 — Downstream validation risk: no demo**

- Severity: medium
- Source: [repo](https://github.com/continuedev/continue)
- Notes: No demo/sandbox install has been executed in downstream validation. User must verify before production use.

**P9 — No sandbox install executed yet**

- Severity: medium
- Source: [repo](https://github.com/continuedev/continue)
- Notes: Security-sensitive users should run their own sandbox install before granting filesystem or credential access.

**P10 — Scoring risk: no demo**

- Severity: medium
- Source: [repo](https://github.com/continuedev/continue)
- Notes: If no demo exists, the risk score should be treated as elevated until proven otherwise.

**P11 — Config error with Ollama Cloud**

- Severity: medium
- Source: [GitHub issue #12370](https://github.com/continuedev/continue/issues/12370)
- Platform: macOS-related conditions
- Notes: API key and config setup with Ollama Cloud can produce non-obvious errors. Verify credentials before assuming a config error is a code bug.

**P12 — Undocumented `.continue/configs` directory support**

- Severity: medium
- Source: [GitHub issue #12377](https://github.com/continuedev/continue/issues/12377)
- Notes: The `.continue/configs` directory behavior is not fully documented. Config changes may have security implications not yet surfaced in docs.

**P13 — Undocumented dynamic model fetching**

- Severity: medium
- Source: [GitHub issue #12376](https://github.com/continuedev/continue/issues/12376)
- Notes: Dynamic model fetching may expose API keys or credentials in ways not covered by the current documentation. Do not assume safe defaults.

**P14 — Undocumented Mercury-2 model Inception provider**

- Severity: medium
- Source: [GitHub issue #12375](https://github.com/continuedev/continue/issues/12375)
- Notes: The Mercury-2 model Inception provider may have credential handling that is not yet documented.

**P15 — PR checks re-post stale task IDs to new commits**

- Severity: medium
- Source: [GitHub issue #12382](https://github.com/continuedev/continue/issues/12382)
- Notes: When using Continue for PR review automation, task IDs from a previous commit may be incorrectly re-used. Verify session freshness before trusting results.

**P16 — v1.2.19-vscode API key conditions**

- Severity: medium
- Source: [v1.2.19-vscode release](https://github.com/continuedev/continue/releases/tag/v1.2.19-vscode)
- Notes: API key handling may have changed in this release. Check release notes for breaking changes.

**P17 — v1.2.20-vscode blocking issue**

- Severity: medium
- Source: [v1.2.20-vscode release](https://github.com/continuedev/continue/releases/tag/v1.2.20-vscode)
- Notes: This release may block fresh installs. Verify against release notes before proceeding.

**P18 — v1.3.35-vscode API key conditions**

- Severity: medium
- Source: [v1.3.35-vscode release](https://github.com/continuedev/continue/releases/tag/v1.3.35-vscode)
- Notes: API key conditions apply in this release. Review release notes.

**P19 — v1.3.36-vscode blocking issue**

- Severity: medium
- Source: [v1.3.36-vscode release](https://github.com/continuedev/continue/releases/tag/v1.3.36-vscode)
- Notes: This release may block fresh installs. Verify against release notes before proceeding.

---

## Doramagic Source Extract

Project: `continuedev/continue`

21 potential pitfalls found; 0 high/blocking confirmed; top priority: install pitfall — `tcsh` shell breaks hardcoded `-l` flag in terminal commands.

All 21 entries above are derived from GitHub community evidence, release notes, and downstream validation signals. Each entry links to its source. Do not treat any entry as a confirmed bug — always verify against the linked source before acting.
