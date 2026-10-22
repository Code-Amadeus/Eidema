# Eidema

**Memory & Persona Runtime for AI Agents**

Eidema is a project for persistent memory and persona continuity in AI applications. It originates in [Amadeus](https://github.com/Code-Amadeus/Amadeus), with reuse by other host applications as a design goal.

## Status

**Design phase.** There is no installable runtime or stable API yet.

The first version focuses on **memory**. Host applications continue to use their existing persona settings and response models. Relationship modeling, learned interaction habits, and automatic persona evolution are future work.

## V1 scope

- Cross-session recall with identifiable sources and explicit access scope.
- User-directed remembering, inspection, correction, and forgetting.
- Optional background memory formation and consolidation with bounded costs.
- Consistent invalidation across memories, summaries, indexes, and in-flight work.
- Integration with host-owned identity, permissions, and authoritative state.

The first implementation milestone will establish the complete explicit-memory lifecycle before adding optional automatic formation.

Remembering a shared event does not imply computing a relationship state. Explicit user preferences can be retained without inferring a personality or relationship change.

## Design documents

- [V1 memory responsibilities and boundaries (中文)](docs/design/v1-memory-boundaries.md) — agreed product scope, ownership, lifecycle, acceptance journeys, and open design questions.

Data structures, storage, retrieval, APIs, and concrete resource budgets remain under discussion. The repository documents intended behavior, not implemented capabilities.

## Direction

Memory and persona are intended to work together within one project. V1 establishes the source, scope, validity, and retrieval foundations that later persona features can consume.

The host remains responsible for identity, access grants, execution permissions, and authoritative application facts. Model-generated interpretations do not create execution authority.

Eidema will draw on established memory-system designs and reuse suitable infrastructure components while maintaining its own product semantics.

## 中文简介

Eidema 是一个面向 AI 应用的记忆与人格项目，起源于 Amadeus，并以独立复用为设计目标。

**第一版先解决记忆。** 人格沿用宿主现有配置；关系状态、互动习惯成长与自动人格演化后置。用户应能跨会话召回、查看、纠正和遗忘记忆，后台形成与整理应具有清楚的范围和成本边界。

已确认的方向见[初版记忆边界设计](docs/design/v1-memory-boundaries.md)。数据结构、存储、检索和预算方案仍在讨论，目前尚未开始运行时实现。

