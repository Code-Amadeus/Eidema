# Eidema

**Memory & Persona Runtime for AI Agents**

Eidema explores how persistent memory, configurable personas, and shared experiences can work together to give AI agents continuity across conversations.

A project by [Code-Amadeus](https://github.com/Code-Amadeus), developed alongside [Amadeus](https://github.com/Code-Amadeus/Amadeus) with reuse in other applications as a design goal.

## Status

**Design phase.** This repository is a project placeholder. There is no installable runtime or stable API yet; the capabilities below describe the intended scope.

## Intended scope

- Cross-session recall grounded in identifiable sources.
- User-controlled preferences and configurable character personas.
- Shared experiences and relationship continuity, with explicit scope.
- Background memory formation and consolidation with bounded resource use.
- User-facing inspection, correction, and forgetting.
- Integration with different models and host applications.

## Design direction

Memory and persona are designed together, with distinct responsibilities in one project:

- **Memory** manages retained experiences, preferences, provenance, retrieval, consolidation, and lifecycle.
- **Persona** combines user-defined character settings with relevant memories and relationship context to guide expression.

The host application remains responsible for identity, access scope, execution permissions, and authoritative application state. Learned interpretations do not create new execution authority.

The implementation will draw on established memory-system designs and reuse suitable infrastructure libraries. Storage, interfaces, scheduling, and packaging will be decided through concrete use cases and evaluation.

## Questions under discussion

- Which memories are shared across characters, and which belong to a particular relationship or project?
- Which persona traits remain user-controlled, and which aspects may evolve through experience?
- What should be remembered automatically, and what should require an explicit user request?
- How do correction and forgetting propagate through summaries, indexes, and background work?
- What latency, token, and device-resource budgets should apply?

## 中文简介

Eidema 是一个面向 AI 应用的记忆与人格模块项目，起源于 Amadeus，并以独立复用为设计目标。

我们希望将跨会话记忆、用户自定义人格、共同经历与关系延续一起设计，同时保留清晰的职责边界和可控的运行开销。用户应能查看、纠正和遗忘记忆。

项目目前处于设计阶段，本仓库仅作占位，尚未提供可安装实现或稳定接口。
