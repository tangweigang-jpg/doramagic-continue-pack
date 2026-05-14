# DIFFERENTIATION.md — continue Doramagic Pack

## Why This Doramagic Pack Is Different

| Dimension | Upstream `continuedev/continue` | This Doramagic Pack |
|-----------|--------------------------------|---------------------|
| **Format** | VS Code extension, JetBrains plugin, CLI | Portable AGENTS.md + CLAUDE.md for AI coding agent hosts |
| **First-run verification** | None — extension loads and hopes for the best | Smoke check eval confirms agent understands the pack before claiming success |
| **Failure recovery** | GitHub issues scattered across 21+ problem reports | Pitfall log with top-3 immediately actionable, full index navigable |
| **Boundary enforcement** | No agent-level permission model | Explicit boundary risk card + boundary eval that tests refusal of unapproved actions |
| **Credential safety** | Config file is documented but credential traps are not | Pitfall #11 specifically calls out Ollama Cloud config errors; agent is instructed not to ask for keys |
| **Shell compatibility** | Known issue: `tcsh` breaks CLI (`-l` flag) — open issue | Pitfall #1 explicitly surfaces this; recovery step provided |
| **PR automation safety** | Known issue: stale task IDs re-post to new commits | Pitfall #15 documents this; agent instructed to verify session freshness |
| **Host portability** | Tied to VS Code / JetBrains / terminal | AGENTS.md works with Claude Code, Codex, and other agent hosts that read host instruction files |
| **Eval suite** | None included | Three evals: smoke (understanding), boundary (refusal), failure (recovery) |
| **Chinese language** | English only | Bilingual: English + Simplified Chinese (README.zh-CN.md) |

## What This Pack Deliberately Does Not Do

- Not an official mirror or fork of continuedev/continue
- Not a generic starter or awesome list
- Not an SEO backlink repo
- Not a plugin installation guide (use upstream docs for that)
- Not a replacement for the upstream project — it is a governance and recovery layer on top of it

## Why This Pack Exists

When an AI coding agent is asked to "use Continue," it typically:
1. Assumes the tool is installed without checking
2. Runs `npm i -g @continuedev/cli` without checking `$SHELL`
3. Claims success before verifying the CLI responds
4. Accesses credentials or filesystem without explicit approval
5. Fails silently and offers no recovery path

This pack exists to close that gap — giving agents a source-controlled, eval-backed, pitfall-logged way to work with Continue.
