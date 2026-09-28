# STATUS — OpenCLI project file lifecycle

State: **BOOTSTRAPPED / JEFA CANDIDATE NOT YET CREATED**
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
2. Create one dedicated OpenCLI Jefa conversation in the common Jefas Project as READ-ONLY CANDIDATE.
3. Record its CID in `.pi/JEFA-BINDING.md` with state CANDIDATE.
4. Write project-local Nudger policy pointing at that candidate binding, but do not start the process.
5. After π multi-project robustness passes, Arquitecta changes binding to ACTIVE, starts Nudger, verifies first live cycle, and lets Jefa execute GOAL.
