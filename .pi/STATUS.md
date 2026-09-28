# STATUS — OpenCLI project file lifecycle

State: **BOOTSTRAPPED / GEN-1 CANDIDATE RETIRED / GEN-2 PENDING**
Last reconciled: 2026-09-28

## Current truth

- GitHub fork exists: `arumihsnek/OpenCLI`.
- Canonical local repo: `/home/ubuntu/code/OpenCLI`.
- `origin` -> user fork; `upstream` -> `jackwener/OpenCLI`.
- Baseline commit: `24136945847afbfad266c6c46a8cd335377f9112`.
- Baseline package version: OpenCLI 1.8.8.
- Current `upstream/main` is exactly `24136945847afbfad266c6c46a8cd335377f9112`; the project branch is 3 π-control commits ahead and **0 commits behind** upstream.
- Upstream package/CLI version is `1.8.8`; installed CLI is also `1.8.8`.
- Upstream `1.8.8` carries browser extension `1.0.24`, while the currently staged/runtime extension artifact is `1.0.23`; this mismatch is recorded and must be reconciled through a controlled smoke, not by blind mid-experiment replacement.
- Existing ChatGPT adapter exposes `project-file-add`.
- No `project-file-remove/delete` command exists in current adapter/help.
- Existing `project-file-add` uploads and verifies appearance; it does not implement replace semantics.
- `ask/send` currently expose image attachments, not arbitrary document `--file` attachments.
- Production installed OpenCLI remains untouched.
- Multi-Projects post-sync readiness is currently **0/3 after a material R3 hydration/readiness failure**; real Jefa activation remains blocked until the π-core robustness battery is durably clean.

## Next

1. Commit this bootstrap on project branch.
2. Jefa candidate created and read-only bootstrap verified: `6abaab6d-dc38-83ed-ada4-8f14f0aafc4e`.
3. Binding records generation 1 as CANDIDATE; no operational authority.
4. Project-local Nudger policy is present but no Nudger process is started.
5. After π multi-project robustness passes, Arquitecta changes binding to ACTIVE, starts Nudger, verifies first live cycle, and lets Jefa execute GOAL.


## Candidate generation-1 retirement — 2026-09-28

Generation-1 candidate CID `6abaab6d-dc38-83ed-ada4-8f14f0aafc4e` is retired after DF-001 exposed a shared-Terminal authority violation during the candidate period. The exact actor attribution is ambiguous, so the defect is classified at the transport/session authority boundary rather than blamed on the candidate model.

The unexpected commit `87cc0592` is preserved because its content was correct and its provenance is material DogFood. A generation-2 candidate will be created **without any tool use** before ACTIVE. Activation remains blocked by π multi-project robustness.


## Maintenance invariant

OpenCLI is expected to change as supported websites change. Before each implementation unit the Jefa must fetch/compare upstream and keep this fork close to `upstream/main`. A stale private adapter is a defect.

Runtime updates are intentionally controlled rather than blindly automatic: validate the upstream CLI/adapter/extension tuple with tests and an authenticated disposable smoke, then promote it. Keep a rollback artifact/version available for the currently working tuple.
