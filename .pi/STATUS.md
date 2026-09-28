# STATUS — OpenCLI project file lifecycle

State: **BOOTSTRAPPED / JEFA CANDIDATE READ-ONLY**
Last reconciled: 2026-09-28

## Current truth

- GitHub fork exists: `arumihsnek/OpenCLI`.
- Canonical local repo: `/home/ubuntu/code/OpenCLI`.
- `origin` -> user fork; `upstream` -> `jackwener/OpenCLI`.
- Baseline commit: `24136945847afbfad266c6c46a8cd335377f9112`.
- Baseline package version: OpenCLI 1.8.8.
- Existing ChatGPT adapter exposes `project-file-add`.
- No `project-file-remove/delete` command exists in current adapter/help.
- Existing `project-file-add` uploads and verifies appearance; it does not implement replace semantics.
- `ask/send` currently expose image attachments, not arbitrary document `--file` attachments.
- Production installed OpenCLI remains untouched.
- Multi-Projects post-sync readiness is currently not yet closed; real Jefa activation remains blocked by that gate.

## Next

1. Commit this bootstrap on project branch.
2. Jefa candidate created and read-only bootstrap verified: `6abaab6d-dc38-83ed-ada4-8f14f0aafc4e`.
3. Binding records generation 1 as CANDIDATE; no operational authority.
4. Project-local Nudger policy is present but no Nudger process is started.
5. After π multi-project robustness passes, Arquitecta changes binding to ACTIVE, starts Nudger, verifies first live cycle, and lets Jefa execute GOAL.
