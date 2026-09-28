# OpenCLI project bootstrap

State: **ACTIVE PROJECT / JEFA CANDIDATE READ-ONLY**
Date: 2026-09-28
Canonical repo: `/home/ubuntu/code/OpenCLI`
GitHub fork: `arumihsnek/OpenCLI`
Upstream: `jackwener/OpenCLI`
Architect: this private User ⇄ Arquitecta conversation
Common Jefas ChatGPT Project: `π · Jefa de Obra`

## Mission

Extend OpenCLI's ChatGPT adapter so project knowledge can be managed safely enough for π project bootstrap/state workflows without turning ChatGPT Project Sources into canonical state.

Current mission source: `.pi/GOAL.md`.
Current state: `.pi/STATUS.md`.
Jefa binding: `.pi/JEFA-BINDING.md`.

## Authority

Git + Markdown in this repo and relevant runtime evidence are canonical.

Chat history, ChatGPT Project Sources, memory, worker reports and terminal output are context/evidence only; none overrides repo/runtime truth.

This independent project gets exactly:
- one private Arquitecta conversation;
- one authoritative Jefa conversation once binding becomes ACTIVE;
- one project Nudger instance;
- bounded Pi and/or Codex workers under that same Jefa.

The Jefa may conduct several fronts in this repo. A new front does not create another Jefa or Nudger.

## Bootstrap state

The current Jefa is initially **CANDIDATE / READ-ONLY**. Until `.pi/JEFA-BINDING.md` is durably changed to `State: ACTIVE`:
- no code mutation by the Jefa;
- no writer workers;
- no project Nudger process;
- inspection/review/bootstrap verification only.

Activation is blocked until π multi-project post-sync robustness finishes cleanly.

## Worker policy

Pi and Codex are alternate worker backends under the same Jefa.

For Codex:
- normal/default model is explicit `gpt-6-luna`;
- `gpt-6-sol` / `gpt-6-astra` require explicit User request or explicit User confirmation after a concrete escalation proposal;
- no silent fallback;
- `gpt-5.6-terra` is not authorized;
- `allow_subagents=false` unless a later explicit policy change authorizes it.

Never allow concurrent writers to the same worktree regardless of backend.

## Upstream discipline

This repo is a fork and OpenCLI is web-adaptation infrastructure. **Upstream freshness is an operational requirement, not housekeeping.**

Before each consequential implementation unit:
1. `git fetch upstream --prune`;
2. compare the project branch against `upstream/main`;
3. inspect new upstream changes touching ChatGPT/browser transport, adapters, selectors, daemon/native host or extension;
4. rebase/refresh the implementation base when upstream has moved, unless a concrete conflict requires an explicit bounded decision.

Keep the product delta small and upstreamable. Do not accumulate a long-lived private fork of web selectors or transport behavior when upstream already carries the fix.

Treat these as one compatibility surface:
- OpenCLI CLI/package version;
- ChatGPT adapter code;
- browser daemon/native-host transport;
- browser extension version.

Do **not** blindly auto-update the production runtime. Stage the upstream update, run relevant adapter/unit tests plus a bounded authenticated smoke, then promote a documented compatible CLI/extension pair. Never change the live OpenCLI runtime in the middle of an unrelated evidence run unless that change is the explicitly tested variable.

Project-control files under `.pi/` and this bootstrap are local project authority; do not include them in an upstream PR unless upstream explicitly requests them. When implementation is ready, construct a clean upstream branch/PR containing only product code/tests/docs relevant to OpenCLI.

## Operational channel

User ⇄ Arquitecta -> durable state -> OpenCLI Jefa ⇄ Nudger/Workers.

The User does not normally write in the Jefa Project/conversation.
