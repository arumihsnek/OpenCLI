# Operational conductor binding

Date: 2026-09-28
Role: Jefa de Obra
Binding generation: 1
State: CANDIDATE

## Active binding

- conversation_id: `PENDING`
- conversation_url: `PENDING`
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
