# continue Doramagic Pack

Pack version: `v1.0.0` · Last updated: `2026-05-14`

[![Pack v1.0.0](https://img.shields.io/badge/pack-v1.0.0-blue)](./CHANGELOG.md) · [![License](https://img.shields.io/github/license/tangweigang-jpg/doramagic-continue-pack)](./LICENSE) · [![Issues](https://img.shields.io/github/issues/tangweigang-jpg/doramagic-continue-pack)](https://github.com/tangweigang-jpg/doramagic-continue-pack/issues)

Languages: English | [中文](./README.zh-CN.md)

## Copy / Run / Verify

1. Copy `AGENTS.md` into your AI coding agent host.
2. Open `06_EVALS/smoke_check.md` and run the prompt.
3. If it fails, open `03_PITFALL_LOG.md` (top 3 pitfalls are listed first).

Quick copy: `cp AGENTS.md /path/to/agent/`

---

## The Problem

You want an AI coding agent that actually understands your codebase — not just a chat sidebar that guesses. Continue is the open-source AI coding agent that embeds in VS Code and JetBrains, but:

- The VS Code extension silently fails on certain shell configs (`$SHELL=/bin/tcsh`, [issue #12378](https://github.com/continuedev/continue/issues/12378))
- The JetBrains plugin has release-specific quirks across v1.0.67 through v1.3.x
- Credential/config errors with Ollama Cloud are easy to trigger and hard to diagnose
- PR check sessions can re-post stale task IDs to new commits instead of spawning fresh sessions

**You need a verified, source-controlled workflow — not a "just install it and hope."**

---

## What This Pack Gives You

An independent capability pack for `continuedev/continue`: host instructions, prompt preview, evals, pitfalls, and recovery rules you can load into any AI coding agent.

Copy `AGENTS.md` into your agent host, run the smoke check, and if something breaks — the pitfall log tells you exactly what went wrong and how to recover.

> This is an independent capability pack. It is not affiliated with or endorsed by continuedev/continue unless explicitly stated.

Quick links:
[Start](./AGENTS.md) · [Prompt](./01_PROMPT_PREVIEW.md) · [Evals](./06_EVALS/) · [Pitfalls](./03_PITFALL_LOG.md) · [Quick Start](./00_QUICK_START.md)

---

## When This Pack Helps

Use this pack when you want to:

- Load Continue into an AI coding agent as a source-controlled workflow with policy checks
- Run eval prompts before claiming the upstream tool is installed or working
- Recover from setup, permission, or runtime failures using a documented pitfall log
- Get boundary and risk signals before your agent takes unsafe actions

---

## What You Get

| File | Purpose |
|------|---------|
| `AGENTS.md` | Host instructions for AI coding agents (Claude Code, Codex, etc.) |
| `CLAUDE.md` | Claude Code-specific runtime instructions |
| `01_PROMPT_PREVIEW.md` | Copyable prompt for pre-install experience |
| `00_QUICK_START.md` | Two-minute path from zero to first check |
| `06_EVALS/smoke_check.md` | Acceptance check: agent understands the pack |
| `06_EVALS/boundary_check.md` | Boundary check: agent refuses unapproved actions |
| `06_EVALS/failure_check.md` | Failure check: agent recovers from broken install |
| `03_PITFALL_LOG.md` | Top 3 pitfalls + full navigable pitfall index |
| `04_BOUNDARY_RISK_CARD.md` | Explicit permission boundaries and stop conditions |
| `ops/GITHUB_METADATA.md` | Repo topics, description, and issue settings |

---

## AGENTS.md for Claude Code and AI Coding Agents

Use `AGENTS.md` for agent hosts that support repository instructions. Use `CLAUDE.md` when Claude Code is the target host.

## continuedev/continue Pitfalls and Recovery

Start with `03_PITFALL_LOG.md` when setup, permissions, runtime behavior, or verification fails. The top 3 actionable pitfalls are listed first.

---

## Source Attribution

This pack was assembled by [Doramagic](https://doramagic.ai).

- Upstream: https://github.com/continuedev/continue
- Upstream license: Apache-2.0
- Pack contents: prompts, host instructions, checks, guardrails, and validation notes

If this pack helps your agent work from evidence instead of guesses, star the repo so future updates are easier to find. Open an issue for bugs, usage questions, or new pitfall reports.
