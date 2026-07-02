# Awesome Smithers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of projects, workflow packs, examples, and integrations built with Smithers, the durable orchestration runtime for agentic workflows.

Smithers workflows are usually TypeScript or TSX files that compose tasks, agents, approval gates, loops, branches, durable checkpoints, and structured outputs. This list focuses on public projects that use those primitives in useful or interesting ways.

Last researched: 2026-07-02.

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
- [smithers-orchestrator on npm](https://www.npmjs.com/package/smithers-orchestrator) - The published runtime package used by most standalone workflows.

## Apps and Control Planes

- [Burns](https://github.com/l3wi/burns) - Workspace-first local control plane for authoring, running, and supervising Smithers workflows across real repositories. A strong example of how to document a Smithers-adjacent app: it clearly separates Smithers runtime responsibilities from the surrounding workspace, daemon, UI, desktop shell, and CLI.

## Workflow Engines and Packs

- [Agentix](https://github.com/AbdelStark/agentix) - Opinionated RFC-to-production orchestrator with DDD, BDD, TDD, role-based agents, policy gates, telemetry, and a conflict-aware merge queue.
- [Era](https://github.com/ClementWalter/era) - Generic, project-agnostic multi-phase development workflow engine with research, plan, implementation, testing, review, fix, and final review phases.
- [gsmithers](https://github.com/smithersai/gsmithers) - Port of gstack-style AI engineering workflows to typed Smithers TSX workflows with explicit nodes, Zod outputs, checkpoints, and event logs.
- [Local Isolated Ralph / Fabrik](https://github.com/SamuelLHuber/local-isolated-ralph) - Kubernetes-native Smithers workflow runner that targets local and CI execution through k3s Jobs and CronJobs.
- [Ralphinho](https://github.com/enitrat/ralphinho) - Multi-agent development workflows for spec-driven implementation and review discovery, with optional Linear handoff.
- [smithers-workflows](https://github.com/Eikix/smithers-workflows) - Repeatable workflow library for implementation, validation, review, GitHub Actions babysitting, and PR babysitting.
- [Super Ralph](https://github.com/roninjin10/super-ralph) - Reusable ticket-driven development workflow with multi-agent review loops, jj-native worktrees, progress reporting, and speculative merge queue semantics.

## Domain Projects

- [Cairo Coder](https://github.com/KasarLabs/cairo-coder) - AI-powered Cairo smart contract generator and RAG service; listed in the Smithers ecosystem docs as using Smithers with Claude and Codex agents.
- [MealPrepClaw nutrition-agent](https://github.com/roninjin10/MealPrepClaw/tree/main/nutrition-agent) - Durable meal planning and grocery workflow with Smithers TSX workflows, approval gates, MCP sidecars for health data, Instacart, and food vision.
- [VibeAudit](https://github.com/aviggiano/vibeaudit) - AI-assisted security review orchestrator that runs audit strategies in parallel, deduplicates findings, triages them, and emits a final report.

## Samples and Learning

- [smithers-samples](https://github.com/dennisonbertram/smithers-samples) - Runnable, live-verified sample workflows covering fundamentals, durable resume, human approval, memory, retries, scorers, evals, routing, review, ETL, and fix-until-green loops.
- [smithers-toy](https://github.com/amiller/smithers-toy) - Toy Smithers experiments, including interactive demos and exploratory workflows.

## Integrations and Benchmarks

- [elizaOS Smithers benchmark adapter](https://github.com/elizaOS/eliza/tree/main/packages/benchmarks/smithers-adapter) - Benchmark adapter that lets elizaOS benchmark harnesses run against Smithers as an agent harness.

## Embedded Workflows

These projects are not primarily Smithers products, but have public Smithers workflows or workflow experiments worth studying.

- [Agent CAPTCHA](https://github.com/ClementWalter/agent-captcha) - Agent-only posting protocol with cryptographic receipts; includes public `.smithers` workflow files for development and validation flows.
- [labor.fun expense workflow](https://github.com/BreadchainCoop/labor.fun/blob/main/orchestration/workflows/expense.tsx) - Example of Smithers as a long-lived, human-in-the-loop state machine for expense approval and reimbursement.

## Research Notes

This first cut was assembled from:

- Smithers ecosystem docs.
- Web search for Smithers projects.
- GitHub repo and code search for `smithers-orchestrator`, `.smithers/workflows`, and public Smithers workflow references.

Good candidates should be public, directly use Smithers, and have enough readable context that a newcomer can understand why the project is useful.

## Contributing

Additions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a PR.
