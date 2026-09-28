# OpenCLI project DogFood

## DF-001 — candidate-period cross-authority Terminal write

Date: 2026-09-28
State: **PRESERVED / BLOCKS GEN-1 CANDIDATE**

### Observation

After generation-1 Jefa candidate `6abaab6d-dc38-83ed-ada4-8f14f0aafc4e` had been created as explicitly READ-ONLY / CANDIDATE, an unexpected ChatGPT `terminal_send` used shared Terminal MCP session `b8a6f394-193e-4f61-bd2b-fd80d1b0ba55` to edit `.pi/STATUS.md`, commit and push:

`87cc0592 chore(pi): pin OpenCLI activation to multi-project readiness`

The edit was factually correct, but no operational writer was authorized for this project. Terminal MCP audit records the exact command at 2026-09-28T18:05:17Z. The same Terminal session subsequently contains π-core Supervisor test activity, so conversation-level attribution is not sufficiently strong to claim which ChatGPT conversation issued the write.

### Meaning

The demonstrated defect is authority isolation, not content correctness.

Chat/CDP binding isolation alone is insufficient if an operational ChatGPT actor can reuse a pre-existing Terminal MCP session whose cwd/capabilities are not project-bound. A CANDIDATE Jefa must not obtain mutation authority indirectly through a shared terminal session.

### Disposition

- preserve commit `87cc0592` in history as evidence; do not rewrite it away;
- retire generation-1 candidate;
- generation-2 candidate must be created inert, with **no tool use before ACTIVE**;
- no OpenCLI Nudger process or writer worker starts before the π multi-project readiness campaign proves the terminal-session authority boundary;
- after activation, Jefa may use only Terminal sessions explicitly created/claimed for the OpenCLI project under the adopted project-local terminal ownership rule;
- no scheduler, registry or new control plane is implied by this observation.
