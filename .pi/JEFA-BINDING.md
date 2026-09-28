# Operational conductor binding

Date: 2026-09-28
Role: Jefa de Obra
Binding generation: 2
State: CANDIDATE

## Active binding

- conversation_id: `6abaafc5-2374-83eb-89ac-f3d49b190c41`
- conversation_url: `https://chatgpt.com/g/g-p-6ab83915ed0481919d8a3e2d060abad0-p-jefa-de-obra/c/6abaafc5-2374-83eb-89ac-f3d49b190c41`
- project: `π · Jefa de Obra`
- project_id: `opencli`
- authority: no operational authority until this file is explicitly transitioned to ACTIVE

## Retired bindings

- generation 1 conversation_id: `6abaab6d-dc38-83ed-ada4-8f14f0aafc4e`
  - state: RETIRED
  - reason: DF-001 / D54 exposed shared-Terminal session authority leakage during candidate bootstrap; exact ChatGPT actor attribution remained ambiguous.

## Invariant

A responsive candidate chat is not an active conductor.

Before ACTIVE:
- no tool use by the candidate;
- no repo/runtime mutation;
- no worker dispatch;
- no Nudger process.

Generation 2 was created inert and did not read the repo. Full repo re-ground happens only after a durable ACTIVE transition and after the multi-project Terminal-session authority blocker is resolved and proven.
