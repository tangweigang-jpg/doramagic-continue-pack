# AGENTS.md — continue Doramagic Pack

## Purpose

Use this pack to help an AI coding agent work with `continuedev/continue` safely and verifiably. This pack does not install Continue — it provides host instructions so an AI agent can load, verify, and recover from common failure modes.

---

## When To Load This Pack

Load `AGENTS.md` when any of the following is true:

| Scenario | Example |
|----------|---------|
| User asks to set up Continue as a coding agent workflow | "I want to use Continue to review PRs in my CI pipeline" |
| Agent is about to run `npm i -g @continuedev/cli` | Agent should first verify shell compatibility (see Pitfall #1) |
| Agent encounters a failed install or silent extension load failure | Agent should consult `03_PITFALL_LOG.md` before retrying |
| Agent needs to use external tools, network, or credentials | Agent must check `04_BOUNDARY_RISK_CARD.md` first |
| Agent is about to claim Continue is "working" | Agent must run `06_EVALS/smoke_check.md` first |

Do NOT load this pack when:
- The user is just asking about Continue's features (use upstream docs instead)
- The task does not involve Continue or AI coding agent workflow governance

---

## How To Use (Step by Step)

### Step 1: Load the pack

Read `AGENTS.md` and `00_QUICK_START.md` before taking any action.

### Step 2: Clarify the goal

Confirm:
- Is this about loading Continue as a coding-agent workflow?
- Does the user have a target host (Claude Code, Codex, custom CLI)?
- What safety boundary applies (filesystem, credentials, network)?

### Step 3: Run the smoke check conceptually

Before calling any external tool, open `06_EVALS/smoke_check.md` and run the prompt mentally:
- Can the agent restate the task?
- Can the agent identify boundaries?
- Does the agent propose a verification step?
- Does the agent avoid claiming success without evidence?

### Step 4: Check pitfalls before external tool use

Before running `npm i -g @continuedev/cli` or installing any extension, consult `03_PITFALL_LOG.md`:

- **Pitfall #1** (HIGH priority): `$SHELL=/bin/tcsh` causes hardcoded `-l` flag failures — affects Linux/macOS installs
- **Pitfall #2**: VS Code extension silently fails to load on Windows with certain shell configs
- **Pitfall #3**: JetBrains plugin v1.0.67 has release-specific quirks

### Step 5: Get explicit approval for risky actions

Before using browser, network, filesystem, or credentials — state the action and wait for approval. See `04_BOUNDARY_RISK_CARD.md`.

### Step 6: Verify before claiming success

Run at least one eval from `06_EVALS/`:
- `smoke_check.md` — agent understands the pack
- `boundary_check.md` — agent refuses unapproved actions
- `failure_check.md` — agent recovers from broken install

---

## Failure Recovery Table

| Eval Failure | Expected Signal | Recovery Action |
|-------------|-----------------|-----------------|
| `smoke_check.md` | Agent claims Continue is installed without evidence | Stop. Open `03_PITFALL_LOG.md`. Retry with explicit boundaries. |
| `boundary_check.md` | Agent proceeds without approval | Stop. Rewrite host instructions to make boundary explicit. |
| `failure_check.md` | Agent invents facts or ignores pitfall log | Update `03_PITFALL_LOG.md` with clearer recovery item. |

---

## Allowed Actions

- Read files in this pack
- Ask clarifying questions
- Produce a plan
- Run only user-approved verification commands
- Record failures in the pitfall log format

## Disallowed Actions

- Do not claim official endorsement
- Do not access secrets by default
- Do not send messages, publish, purchase, delete, or modify external systems without explicit user approval
- Do not claim the upstream tool works until an acceptance check passes

## Verification Checklist

- [ ] Read `00_QUICK_START.md`
- [ ] Run `06_EVALS/smoke_check.md` mentally before claiming success
- [ ] Check `03_PITFALL_LOG.md` before escalating
- [ ] Check `04_BOUNDARY_RISK_CARD.md` before using external tools

## Failure Report Format

If verification fails, stop and report:
```
- Which eval failed:
- Expected result:
- Actual result:
- Suspected cause:
- Recovery step from 03_PITFALL_LOG.md:
```

## Source / Risk Reminder

This is an independent Doramagic pack. Use `SOURCE_MAP.md` for evidence and source links.
