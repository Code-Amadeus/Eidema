# Eidema

**Memory & Persona Runtime for AI Agents**

Eidema is a project for persistent memory and persona continuity in AI applications. It originates in [Amadeus](https://github.com/Code-Amadeus/Amadeus), with reuse by other host applications as a design goal.

## Status

**Design phase.** There is no installable runtime or stable API yet.

The initial technology direction is **Python + SQLite**, with related tables in one device-local database per dataset. The concrete schema and interfaces remain design proposals.

The first version focuses on **memory**. Host applications continue to use their existing persona settings and response models. Relationship modeling, learned interaction habits, and automatic persona evolution are future work.

## V1 scope

- Cross-session recall with identifiable sources and explicit access scope.
- User-directed remembering, inspection, correction, and forgetting.
- Optional background memory formation and consolidation with bounded costs.
- Consistent invalidation across memories, summaries, indexes, and in-flight work.
- Integration with host-owned identity, permissions, and authoritative state.

The first implementation milestone will establish the complete explicit-memory lifecycle before adding optional automatic formation.

Remembering a shared event does not imply computing a relationship state. Explicit user preferences can be retained without inferring a personality or relationship change.

Deleting a chat retains explicitly saved memories through minimal save receipts, authorized by the host and stored atomically with the memory in Eidema. Forgetting is a separate operation. Response preferences can enter as candidates and be reviewed for stable adoption; adoption and per-turn inclusion are separate decisions. Persona definitions and host-executed settings remain host-owned. Memory text never acquires system-level authority.

## Design documents

- [V1 memory responsibilities and boundaries (中文)](docs/design/v1-memory-boundaries.md) — agreed product scope, ownership, lifecycle, acceptance journeys, and open design questions.
- [Persistent-agent scheduling boundaries (中文)](docs/design/persistent-agent-scheduling.md) — future host-owned scheduling, durable work, and its separation from memory maintenance.
- [V1 data and runtime proposal (中文)](docs/design/v1-data-runtime-proposal.md) — local Amadeus deployment, retrieval baseline, background costs, and the reasoning for Python + SQLite.
- [V1 data model (中文)](docs/design/v1-data-model.md) — proposed fields, related tables, and worked examples for remembering, correcting, and forgetting.
- [V1 retrieval and context proposal (中文)](docs/design/v1-retrieval-context.md) — FTS5 and multilingual vectors, Chinese-to-Japanese retrieval, context selection, and experimental token and latency budgets.
- [Benchmark references and coverage gaps (中文)](docs/design/benchmark-references.md) — useful external tasks, metrics, and limits; no evaluation runs or custom benchmark design.
- [Runtime paths and persona interaction notes (中文)](docs/design/runtime-paths-discussion.md) — proposed hot, warm, and cold responsibilities, including contextual reasoning and temporary salience; still open for discussion.

Table schemas, storage configuration, retrieval, APIs, and concrete resource budgets remain under discussion. The repository documents intended behavior, not implemented capabilities.

The draft is being held for further consideration. Memory selection and injection should account for interaction and persona, alongside factual recall. The three runtime paths are discussion notes, not a finalized architecture or implementation plan.

The 2026-10-26 review adds host-integration constraints to the existing documents. No implementation milestone, candidate-review schema, or standing-set interface is frozen. A license has not yet been selected; reuse is a design goal, not an assertion that an open-source license has already been granted.

## Direction

Memory and persona are intended to work together within one project. V1 establishes the source, scope, validity, and retrieval foundations that later persona features can consume.

The host remains responsible for identity, access grants, execution permissions, and authoritative application facts. Model-generated interpretations do not create execution authority.

Amadeus is a persistent agent. A dedicated host scheduling and persistent-runtime component is a future requirement; schedule definitions, triggers, recovery, and work dispatch remain separate from Eidema's memory maintenance.

Eidema will draw on established memory-system designs and reuse suitable infrastructure components while maintaining its own product semantics.

V1 targets local Amadeus first. Original-source retrieval and explicit memory form the primary comparison baseline; extraction and consolidation must demonstrate their benefit. Memory evaluation includes behavioral precedent and persona continuity as well as recall quality.

## 中文简介

Eidema 是一个面向 AI 应用的记忆与人格项目，起源于 Amadeus，并以独立复用为设计目标。

**第一版先解决记忆。** 人格沿用宿主现有配置；关系状态、互动习惯成长与自动人格演化后置。用户应能跨会话召回、查看、纠正和遗忘记忆，后台形成与整理应具有清楚的范围和成本边界。

已确认的方向见[初版记忆边界设计](docs/design/v1-memory-boundaries.md)。初版按 Python + SQLite 推进；具体数据表、检索和预算方案仍在讨论，目前尚未开始运行时实现。

初版先服务本地 Amadeus，并保留其他宿主接入能力。[数据与 runtime 讨论稿](docs/design/v1-data-runtime-proposal.md)记录技术方向；[初版数据模型](docs/design/v1-data-model.md)细化同一 SQLite 数据库内各表的字段与关系，表结构和 API 尚未冻结。

删除聊天保留此前明确保存的记忆，遗忘是独立操作。保存凭据由 Host 核准，与记忆一起存入 Eidema。回复偏好可先进入候选，经审查后稳定采用；长期采用与每轮注入分别判断。人设定义及 Host 执行的语言、TTS、权限等设置仍由宿主管理。[检索与上下文方案](docs/design/v1-retrieval-context.md)说明候选、采用视图与主模型上下文的关系。

当前初稿暂留待进一步思考。[Benchmark 参考](docs/design/benchmark-references.md)记录可借鉴指标与覆盖缺口；[热、温、冷路径讨论](docs/design/runtime-paths-discussion.md)保留记忆与人格共同影响提取、注入和交互的方向，尚不冻结架构。

