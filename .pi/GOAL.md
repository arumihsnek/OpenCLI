# GOAL — ChatGPT project file lifecycle

State: **AUTHORIZED / PRE-ACTIVATION**
Date: 2026-09-28

## Outcome

Make OpenCLI able to maintain ChatGPT Project knowledge safely enough for π bootstrap/reference synchronization, while preserving project-local authority boundaries.

## Required product capabilities

### P-1 — upstream freshness gate
Before implementing P0/P1/P2, refresh against `upstream/main` and verify the active OpenCLI runtime compatibility tuple (CLI + ChatGPT adapter + browser extension). If upstream already implements or materially changes the target behavior, adapt the mission rather than duplicating it.

Promotion of an updated CLI/extension to the live OpenCLI runtime requires relevant tests plus a bounded authenticated smoke. Repository freshness may be automatic; production runtime replacement is controlled.


### P0 — project knowledge lifecycle
1. Add a deterministic command to remove a named file/source from one ChatGPT Project, e.g.:
   `opencli chatgpt project-file-remove <name> --id <project>`.
2. Fail closed when:
   - the target Project cannot be verified;
   - zero matching sources exist when strict removal is requested;
   - more than one ambiguous match exists;
   - removal cannot be confirmed afterward.
3. Add tests against stable DOM/API seams, not blind coordinate clicking.

### P1 — safe replace/sync
Provide the smallest safe replacement primitive for a tracked local file, preferably:
`project-file-replace <file> --id <project>`
or an equivalent explicit sync mode.

Required semantics:
- identify existing source by exact filename;
- remove the old source;
- upload the new file using existing `project-file-add`;
- verify the final source set;
- surface partial failure explicitly; never claim atomicity if the product surface cannot provide it.

### P2 — project-specific document context
Investigate and, if small and robust, add arbitrary document attachment support to an exact ChatGPT conversation (`ask/send --file ... --conversation <cid>`) so repo-specific STATUS/ROADMAP/bootstrap snapshots do not need to become Sources shared by every Jefa in the common Project.

This capability must not weaken existing image attachment semantics.

## Acceptance

- unit/adapter tests for remove and replace failure modes;
- live disposable Project proof for add -> replace -> remove with exact postconditions;
- no mutation of the production common Jefas Project during development tests;
- existing ChatGPT adapter test suite remains green;
- upstreamable product commits are separable from π project-control files;
- current installed OpenCLI is not replaced until the feature passes bounded live proof.

## Non-goals

- making ChatGPT Project Sources canonical state;
- adding a scheduler/state database;
- per-project ChatGPT Projects solely to isolate files;
- broad refactor of the ChatGPT adapter unrelated to file lifecycle.
