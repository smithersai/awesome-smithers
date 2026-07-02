# Awesome Smithers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of projects, workflow packs, examples, and integrations built with Smithers, the durable orchestration runtime for agentic workflows.

Smithers workflows are usually TypeScript or TSX files that compose tasks, agents, approval gates, loops, branches, durable checkpoints, and structured outputs. This list focuses on public projects that use those primitives in useful or interesting ways.

Last researched: 2026-07-02.

Entries favor direct Smithers usage with public evidence: a README, docs page, package dependency, published workflow pack, or visible `.smithers` workflow source. Smithers-adjacent projects are included only when that relationship is clear from public source.

## Contents

- [Official](#official)
- [Apps and Control Planes](#apps-and-control-planes)
- [Workflow Engines and Packs](#workflow-engines-and-packs)
- [Domain Projects](#domain-projects)
- [Samples and Learning](#samples-and-learning)
- [Integrations and Benchmarks](#integrations-and-benchmarks)
- [Embedded Workflows](#embedded-workflows)
- [Research Notes](#research-notes)

## Official

- [Smithers](https://github.com/smithersai/smithers) - The core open-source Smithers repo: engine, scheduler, CLI, gateway, workflow pack, components, docs, examples, and e2e tests.
- [Smithers docs](https://smithers.sh) - Product docs, component reference, guides, examples, integration docs, and workflow catalog.

## Apps and Control Planes

- [Acoco](https://acoco.ai) - Autonomous Company Company platform for owning self-running businesses in the broader Smithers ecosystem.
- [Burns](https://github.com/l3wi/burns) - Workspace-first local control plane for authoring, running, and supervising Smithers workflows across real repositories. A strong example of how to document a Smithers-adjacent app: it clearly separates Smithers runtime responsibilities from the surrounding workspace, daemon, UI, desktop shell, and CLI.
- [JJHub](https://github.com/smithersai/jjhub) - Jujutsu-native software forge with a workflow package that wraps Smithers primitives for triggers, tasks, artifacts, caches, and schema-driven workflow authoring.
- [Panopticon](https://github.com/RonTuretzky/vibecode-room) - Spatial AI-agent workspace with a Smithers-backed meta-session, suggestion engine, process manager, and public `.smithers` workflows for agent process experiments.
- [paperclip-smithers](https://github.com/smithersai/smithers-paperclip) - Paperclip-style agent work management app built with Smithers Gateway and workflows for routines, approvals, budgets, imports, exports, and plugin jobs.
- [Smithers Workflow Directory](https://www.smithers.directory/) - Community directory for discovering and installing Smithers workflow packs, with published manifests for repositories such as Ralf workflows and Go review workflows.
- [Smithers TUI](https://github.com/smithersai/tui) - Go terminal interface with seeded Smithers workflows and MCP status handling for Smithers-connected agent sessions.
- [SmithersGUI](https://github.com/smithersai/gui) - Native macOS app for managing Smithers workflows, agent sessions, terminals, and tickets, with public `.smithers` workflows for ticketing, review, and launch flows.
- [svvy](https://github.com/0xpolarzero/svvy) - Strategic coding workbench that routes bounded implementation threads through official Smithers CLI workflow work and durable result handoff.
- [takopi-smithers](https://github.com/smithersai/takopi-smithers) - Telegram bridge and supervisor for long-lived Smithers workflows, including status updates, restart handling, diagnostics, and auto-heal support.

## Workflow Engines and Packs

- [Agentix](https://github.com/AbdelStark/agentix) - Opinionated RFC-to-production orchestrator with DDD, BDD, TDD, role-based agents, policy gates, telemetry, and a conflict-aware merge queue.
- [Era](https://github.com/ClementWalter/era) - Generic, project-agnostic multi-phase development workflow engine with research, plan, implementation, testing, review, fix, and final review phases.
- [gsmithers](https://github.com/smithersai/gsmithers) - Port of gstack-style AI engineering workflows to typed Smithers TSX workflows with explicit nodes, Zod outputs, checkpoints, and event logs.
- [Local Isolated Ralph / Fabrik](https://github.com/SamuelLHuber/local-isolated-ralph) - Kubernetes-native Smithers workflow runner that targets local and CI execution through k3s Jobs and CronJobs.
- [Ralf Smithers Workflows](https://github.com/ralfboltshauser/ralf-workflows) - Directory-publishable workflow pack with bug regression audits, Lighthouse checks, cyber security audits, and Smithers image-generation workflows.
- [Ralphinho](https://github.com/enitrat/ralphinho) - Multi-agent development workflows for spec-driven implementation and review discovery, with optional Linear handoff.
- [smithers-fusions](https://github.com/smithersai/smithers-fusions) - CLI and TypeScript library for model-panel fusions and durable Smithers plan, implement, review, and fix loops with approval gates.
- [smithers-go-review](https://github.com/SamuelLHuber/smithers-go-review) - Installable Smithers workflow for strict Go code review against Go Code Review Comments and Effective Go, returning structured issue reports.
- [smithers-go-review-fix](https://github.com/SamuelLHuber/smithers-go-review-fix) - Go review workflow with a surgical fix loop that addresses one issue per iteration and validates with `go test` and `go vet`.
- [smithers-workflows](https://github.com/Eikix/smithers-workflows) - Repeatable workflow library for implementation, validation, review, GitHub Actions babysitting, and PR babysitting.
- [Super Ralph](https://github.com/roninjin10/super-ralph) - Reusable ticket-driven development workflow with multi-agent review loops, jj-native worktrees, progress reporting, and speculative merge queue semantics.

## Domain Projects

- [AttestMesh](https://github.com/AttestMesh/AttestMesh) - On-chain coordination layer whose deployment workflow uses Smithers to bring up contracts, a webhook, an indexer, nodes, and mesh verification.
- [Cairo Coder](https://github.com/KasarLabs/cairo-coder) - AI-powered Cairo smart contract generator and RAG service; listed in the Smithers ecosystem docs as using Smithers with Claude and Codex agents.
- [MealPrepClaw nutrition-agent](https://github.com/roninjin10/MealPrepClaw/tree/main/nutrition-agent) - Durable meal planning and grocery workflow with Smithers TSX workflows, approval gates, MCP sidecars for health data, Instacart, and food vision.
- [VibeAudit](https://github.com/aviggiano/vibeaudit) - AI-assisted security review orchestrator that runs audit strategies in parallel, deduplicates findings, triages them, and emits a final report.
- [XVI](https://github.com/evmts/xvi) - Ethereum execution client experiment where Smithers orchestrates AI agents that plan, implement, test, and review generated Zig and Effect-TS client code.

## Samples and Learning

- [agentic-hacks](https://github.com/smithersai/agentic-hacks) - Worked translation of agentic engineering habits into durable Smithers workflows covering sequences, parallel fan-out, approvals, events, and memory.
- [smithers-opportunities](https://github.com/SamuelLHuber/smithers-opportunities) - Agent skill that scans coding-agent session history for repeated patterns where Smithers workflows could replace manual sessions.
- [smithers-practice](https://github.com/amiller/smithers-practice) - Reusable Smithers starter kit with research and build-loop workflow templates, a custom monitoring dashboard, and workflow pattern notes.
- [smithers-samples](https://github.com/dennisonbertram/smithers-samples) - Runnable, live-verified sample workflows covering fundamentals, durable resume, human approval, memory, retries, scorers, evals, routing, review, ETL, and fix-until-green loops.
- [smithers-toy](https://github.com/amiller/smithers-toy) - Toy Smithers experiments, including interactive demos and exploratory workflows.
- [Voltaire Effect Example](https://github.com/evmts/voltaire-effect-example) - Compact example repository showing an older Ralph-style Smithers workflow with phases, agent components, SQLite state, and `.smithers` execution logs.

## Integrations and Benchmarks

- [elizaOS Smithers benchmark adapter](https://github.com/elizaOS/eliza/tree/main/packages/benchmarks/smithers-adapter) - Benchmark adapter that lets elizaOS benchmark harnesses run against Smithers as an agent harness.
- [Poolside Skills](https://github.com/poolsideai/skills) - Skill library and eval workbench with Smithers workflow experiments where Pool executes workflow nodes and skills can be installed per node.

## Embedded Workflows

These projects are not primarily Smithers products, but have public Smithers workflows or workflow experiments worth studying.

- [Agent CAPTCHA](https://github.com/ClementWalter/agent-captcha) - Agent-only posting protocol with cryptographic receipts; includes public `.smithers` workflow files for development and validation flows.
- [agent-session-search](https://github.com/benvenker/agent-session-search) - Local MCP server and CLI for searching coding-agent session history, with Smithers workflows for planning, backpressure, grill-me, and review-loop experiments.
- [DAML Tools](https://github.com/stevennevins/daml-tools) - DAML tooling workspace with Smithers prompt scaffolding for generating runnable workflow files from approved workflow designs.
- [distillery](https://github.com/TinyCloudLabs/artifactory) - Transcript-to-artifact system with Smithers workflows for staged rich-media smoke tests, agent runs, feed orchestration, and report generation.
- [labor.fun expense workflow](https://github.com/BreadchainCoop/labor.fun/blob/main/orchestration/workflows/expense.tsx) - Example of Smithers as a long-lived, human-in-the-loop state machine for expense approval and reimbursement.
- [prettymux](https://github.com/patcito/prettymux) - Terminal multiplexer project with public Smithers validation-loop components for implement, validate, and review cycles.
- [smithers-tests](https://github.com/evmts/smithers-tests) - Compact Voltaire release-testing workflow that uses Smithers phases and parallel agents to fan out test work across Git worktrees.

## Research Notes

This first cut was assembled from:

- Smithers ecosystem docs.
- Smithers Workflow Directory.
- Web search for Smithers projects.
- GitHub repo and code search for `smithers-orchestrator`, `createSmithers`, `@jsxImportSource smithers-orchestrator`, `.smithers/workflows`, and public Smithers workflow references.

Good candidates should be public, directly use Smithers, and have enough readable context that a newcomer can understand why the project is useful.

## Contributing

Additions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a PR.
