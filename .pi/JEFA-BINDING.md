# Operational conductor binding

Date: 2026-09-28
Role: Jefa de Obra
Binding generation: 1
State: CANDIDATE

## Active binding

- conversation_id: `6abaab6d-dc38-83ed-ada4-8f14f0aafc4e`
- conversation_url: `https://chatgpt.com/g/g-p-6ab83915ed0481919d8a3e2d060abad0-p-jefa-de-obra/c/6abaab6d-dc38-83ed-ada4-8f14f0aafc4e`
- project: `π · Jefa de Obra`
- project_id: `opencli`
- authority: no operational authority until this file is explicitly transitioned to ACTIVE

## Invariant

A responsive candidate chat is not an active conductor.

Before ACTIVE:
- read-only bootstrap only;
- no worker dispatch;
- no code/repo/runtime mutation;
- no Nudger process.

Activation is an explicit durable transition performed by the project Arquitecta after the multi-project readiness gate passes.
