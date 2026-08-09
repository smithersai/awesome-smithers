# Awesome Smithers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of projects, workflow packs, examples, and integrations built with Smithers, the durable orchestration runtime for agentic workflows.

Smithers workflows are usually TypeScript or TSX files that compose tasks, agents, approval gates, loops, branches, durable checkpoints, and structured outputs. This list focuses on public projects that use those primitives in useful or interesting ways.

Last researched: 2026-08-09.

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
- [Smithers examples folder](https://github.com/smithersai/smithers/tree/main/examples) - 100+ runnable reference workflows in the core repo covering loops, fan-out/fan-in, approvals, gates, evals, ETL, review cycles, retries, and domain automations.
- [smithers.sh/llms-full.txt](https://smithers.sh/llms-full.txt) - Full documentation bundle in a single file for feeding Smithers docs to LLMs and coding agents.
- [smithers.sh/mcp](https://smithers.sh/mcp) - Smithers MCP integration docs for connecting agents to the Smithers control plane over the Model Context Protocol.
- [smthrs npm package](https://www.npmjs.com/package/smthrs) - Published Smithers package and CLI facade for durable coding-agent workflows, Gateway operation, and generated workflow packs. Renamed from `smithers-orchestrator` on 2026-08-01; the old package is frozen at 0.32.0.
- [Smithers Flows](https://github.com/smithersai/flows) - Unreleased standalone Effect-based durable-execution engine: typed flows, journal-backed execution state, content-addressed activities, capability-checked host effects, synchronization, and time-travel protocols, published as the `@smithers/*` package family.
- [template-smithers-product](https://github.com/smithersai/template-smithers-product) - Minimal smithers-orchestrator product-service skeleton deployable to Cloudflare Workers, with a JSX workflow definition, a worker entry with health check, and Alchemy infrastructure-as-code.
- [incur](https://github.com/wevm/incur) - CLI framework for agents and humans that the Smithers CLI is built on (a direct `incur` dependency of the core repo); a great foundation for building agent-friendly command-line tools.

## Apps and Control Planes

- [Burns](https://github.com/l3wi/burns) - Workspace-first local control plane for authoring, running, and supervising Smithers workflows across real repositories. A strong example of how to document a Smithers-adjacent app: it clearly separates Smithers runtime responsibilities from the surrounding workspace, daemon, UI, desktop shell, and CLI.
- [Codeplane Community Edition](https://github.com/smithersai/community) - Archived self-hosted agentic software development service; its `AGENTS.md` describes a "SuperSmithers" product lifecycle running inside Smithers, with `specs/generate.tsx` as a ticket-based Smithers workflow. Historical/read-only.
- [CustomHarness](https://github.com/benvenker/custom-harness) - Local visual workbench for Smithers workflow-pack source and run state, with graph previews, source-backed metadata editing, run starts, and SQLite run inspection.
- [JJHub](https://github.com/smithersai/jjhub) - Jujutsu-native software forge with a workflow package that wraps Smithers primitives for triggers, tasks, artifacts, caches, and schema-driven workflow authoring.
- [paperclip-smithers](https://github.com/smithersai/smithers-paperclip) - Paperclip-style agent work management app built with Smithers Gateway and workflows for routines, approvals, budgets, imports, exports, and plugin jobs.
- [Runyard](https://github.com/roninjin10/runyard) - Self-hosted control plane for agent runs (formerly Smithers Hub): team-defined capabilities surfaced as Smithers workflows, disposable runners that claim and execute runs, approvals resolvable from Web, API, CLI, MCP, or Telegram, and a `run-smithers` supervising wrapper that gives every long-running goal Smithers-managed lineage, retries, and error-fingerprint-based escalation to a human.
- [Smithers Workflow Directory](https://www.smithers.directory/) - Community directory for discovering and installing Smithers workflow packs, with published manifests for repositories such as Ralf workflows and Go review workflows.
- [smithers-directory CLI](https://npmx.dev/package/smithers-directory) - Published CLI for adding Smithers Directory workflow packs by `owner/repo`, with a short `smithers-dir` alias package.
- [smithers-progress](https://github.com/aviggiano/smithers-progress) - Read-only Codex plugin that visualizes local Smithers workflow runs in a right-side panel: directory picker, run selector, progress summary, workflow graph, and node details.
- [Smithers TUI](https://github.com/smithersai/tui) - Go terminal interface with seeded Smithers workflows and MCP status handling for Smithers-connected agent sessions.
- [SmithersGUI](https://github.com/smithersai/gui) - Native macOS app for managing Smithers workflows, agent sessions, terminals, and tickets, with public `.smithers` workflows for ticketing, review, and launch flows.
- [svvy](https://github.com/0xpolarzero/svvy) - Electrobun desktop coding workbench with two independent Smithers usages: a repo-native `workflows/` authoring pack (pinned `smithers-orchestrator`, `Worktree`-isolated implement/test/review loops fanned out in `Parallel` across Codex, Gemini CLI, and Pi agents) that builds svvy itself, and a shipped builtin extension that teaches the app's own agents to drive the official Smithers CLI directly rather than hiding it behind a product wrapper, backed by a runtime task-agent bridge that exposes svvy's coding agent as an `AgentLike` for `<Task agent={...}>`.
- [takopi-smithers](https://github.com/smithersai/takopi-smithers) - Telegram bridge and supervisor for long-lived Smithers workflows, including status updates, restart handling, diagnostics, and auto-heal support.
- [Vibersyn (formerly Panopticon)](https://github.com/RonTuretzky/vibecode-room) ([vibecoderoom.ai](https://vibecoderoom.ai)) - Voice- and gesture-driven ambient idea room where spoken ideas are judged live by a Smithers-scored detector and each accepted idea spawns a durable, steerable Smithers run that builds it into a running app in front of the room, including a self-hosting mode where the room edits its own source behind a Smithers-gated commit. The integration began as a collaboration with Smithers author Will Cory, who built its original Smithers foundation.

## Workflow Engines and Packs

- [Agentix](https://github.com/AbdelStark/agentix) - Opinionated RFC-to-production orchestrator with DDD, BDD, TDD, role-based agents, policy gates, telemetry, and a conflict-aware merge queue.
- [bb-smithers-workflows](https://github.com/benvenker/bb-smithers-workflows) - Native Smithers 0.33 workflow pack shared by BB plugin repositories for plugin verification and release gates; the first third-party pack on the renamed `smthrs` package, installable via `smithers add github:benvenker/bb-smithers-workflows/pack#<sha>` and recorded in `.smithers/packs.lock.toon`.
- [Era](https://github.com/ClementWalter/era) - Generic, project-agnostic multi-phase development workflow engine with research, plan, implementation, testing, review, fix, and final review phases.
- [gsmithers](https://github.com/smithersai/gsmithers) - Port of gstack-style AI engineering workflows to typed Smithers TSX workflows with explicit nodes, Zod outputs, checkpoints, and event logs.
- [Local Isolated Ralph / Fabrik](https://github.com/SamuelLHuber/local-isolated-ralph) - Kubernetes-native Smithers workflow runner that targets local and CI execution through k3s Jobs and CronJobs.
- [Ralf Smithers Workflows](https://github.com/ralfboltshauser/ralf-workflows) - Directory-publishable workflow pack with bug regression audits, Lighthouse checks, cyber security audits, and Smithers image-generation workflows.
- [Ralphinho](https://github.com/enitrat/ralphinho) - Multi-agent development workflows for spec-driven implementation and review discovery, with optional Linear handoff; a fork of Super Ralph below, so the two entries share one lineage rather than representing independent adoptions.
- [smithers-fusions](https://github.com/smithersai/smithers-fusions) - CLI and TypeScript library for model-panel fusions and durable Smithers plan, implement, review, and fix loops with approval gates.
- [smithers-go-review](https://github.com/SamuelLHuber/smithers-go-review) - Installable Smithers workflow for strict Go code review against Go Code Review Comments and Effective Go, returning structured issue reports.
- [smithers-go-review-fix](https://github.com/SamuelLHuber/smithers-go-review-fix) - Go review workflow with a surgical fix loop that addresses one issue per iteration and validates with `go test` and `go vet`.
- [smithers-workflows](https://github.com/Eikix/smithers-workflows) - Repeatable workflow library for implementation, validation, review, GitHub Actions babysitting, and PR babysitting.
- [Super Ralph](https://github.com/roninjin10/super-ralph) - Reusable ticket-driven development workflow with multi-agent review loops, jj-native worktrees, progress reporting, and speculative merge queue semantics.
- [xiv](https://github.com/jacobdcastro/workflows) - Agent-operated CLI wrapping a managed Smithers pack that takes Linear issues to reviewed PRs: implement/validate/review loops, PR-review-round polling, and overnight jj-stacked feature builds, with mixed Claude/Codex cost tiers and a custom Gateway console.
- [ZetisLabs smithers-workflows](https://github.com/ZetisLabs/smithers-workflows) - Centralized workflow pack for GitHub issue dispatch and PR review, with reusable frontend, backend, testing, review, and security agents.

## Domain Projects

- [Aomi Smither](https://github.com/aomi-labs/aomi/tree/main/packages/smither) - On-chain agentic AI harness whose `aomi-smither` CLI/TUI composes a durable Smithers workflow on the fly from natural-language intent: a Zod-typed `BuildPlan` renders into a JSX task graph with deterministic Rust codegen, Claude/Codex curation/review/fix agents (including cross-repo agents), validate/repair loops, select-mode clarify approvals, LLM-judged eval loops, parallel branches, durable `Signal` waits, and an approval-gated deploy. Ships a custom Gateway console UI with TUI/browser-shared durable decisions, runs on bun:sqlite, PGlite, or PostgreSQL backends, and is documented end-to-end by a real-session PoC log covering durability resume, agent rejection/repair, and live deploy; the companion [aomi-sdk](https://github.com/aomi-labs/aomi-sdk) also runs a Smithers coordination workflow in GitHub Actions.
- [AttestMesh](https://github.com/AttestMesh/AttestMesh) - On-chain coordination layer for meshes of mutually-attested dstack (TEE) nodes; uses Smithers for durable, resumable deploy sequencing (contracts, webhook, indexer, Matrix/Postgres-HA/R2-gateway nodes, mesh verification) and, separately, as the delegation boundary for a fail-closed pre-commit security gate: a `Parallel` panel of ephemeral read-only Codex specialists plus a Zod-typed arbiter `Task` that blocks commits containing secrets, backups, or prompt injection.
- [Cairo Coder](https://github.com/KasarLabs/cairo-coder) - AI-powered Cairo smart contract generator and RAG service; listed in the Smithers ecosystem docs as using Smithers with Claude and Codex agents.
- [Chop](https://github.com/evmts/chop) - EVM SDK workspace with a `scripts/chop-workflow` Smithers package for agent-driven codebase review, validation, planning, and ticket-loop work.
- [Distilled (Hourglass Financial)](https://github.com/hourglass-financial/distilled) - Effect-native multi-cloud SDK generator, a fork of `alchemy-run/distilled`, whose Smithers pipeline drives spec update, patch reconcile, regenerate, and test triage for each vendor SDK, escalating to scoped Codex tasks only when a deterministic classifier cannot resolve the drift.
- [Guillotine Mini](https://github.com/evmts/guillotine-mini) - Tiny Zig EVM with Smithers build and fix-spec workflows, Claude/Codex agent adapters, phase docs, and a Smithers submodule-backed pipeline.
- [loklaan/dotfiles](https://github.com/loklaan/dotfiles) - Chezmoi-managed personal dev environment that wires Smithers in as an mcpproxy MCP server plus a decision-gate skill doc, so Claude Code and OpenCode reach for durable workflow runs when work needs crash recovery, retries, human approval gates, or loop-until-pass orchestration, alongside a broader multi-machine agent-session stack.
- [MealPrepClaw nutrition-agent](https://github.com/roninjin10/MealPrepClaw/tree/main/nutrition-agent) - Durable meal planning and grocery workflow with Smithers TSX workflows, approval gates, MCP sidecars for health data, Instacart, and food vision.
- [omokoda-smithers](https://github.com/cryptonomicsed-byte/omokoda-smithers) - smithers-orchestrator wired to the Omo-Koda2 SkillForge: a full `.smithers` pack (`workflows/skillforge-forge.tsx` with `createSmithers`, DDD build, spec-doc, triage, and validation libraries, and native MCP actions) whose durable approval gates replace a file-based review-ticket system.
- [VibeAudit](https://github.com/aviggiano/vibeaudit) - AI-assisted security review orchestrator that runs audit strategies in parallel, deduplicates findings, triages them, and emits a final report.
- [Voltaire](https://github.com/evmts/voltaire) - Ethereum primitives and cryptography workspace whose TypeScript package includes Smithers orchestration dependencies for workflow-backed development work.
- [XVI](https://github.com/evmts/xvi) - Ethereum execution client experiment where Smithers orchestrates AI agents that plan, implement, test, and review generated Zig and Effect-TS client code.
- [ZEVM](https://github.com/evmts/zevm) - Zig Ethereum client with a Smithers docs convergence loop for implementation passes, cold review, fix iterations, product-decision gates, and final summaries.
- [Zurich Verity](https://github.com/ralfboltshauser/zurich-verity) - Hackathon-built continuous security-validation concept that runs a Codex red-team review inside a hand-rolled Docker `SandboxProvider`, gates GitHub PRs on confirmed findings, and proves fixes with a Docker-isolated retest harness.

## Samples and Learning

- [agentic-hacks](https://github.com/smithersai/agentic-hacks) - Worked translation of agentic engineering habits into durable Smithers workflows covering sequences, parallel fan-out, approvals, events, and memory.
- [Better Beads Smithers template](https://github.com/benvenker/skills/tree/main/skills/better-beads/smithers-templates) - Smithers workflow template that fans out graph reviews for behavior contracts, implementation readiness, dependency correctness, and reviewability before synthesizing a polish plan.
- [smithers-directory skill](https://github.com/SamuelLHuber/smithers-directory-skill) - Agent skill and scripts for packaging `.smithers/workflows` into publishable Smithers Directory repositories, generating manifests, and testing install loops.
- [smithers-hello-world-workflows](https://github.com/ralfboltshauser/smithers-hello-world-workflows) - Minimal Smithers Directory workflow pack with a durable hello-world task and manifest for testing the directory install path.
- [smithers-opportunities](https://github.com/SamuelLHuber/smithers-opportunities) - Agent skill that scans coding-agent session history for repeated patterns where Smithers workflows could replace manual sessions.
- [smithers-practice](https://github.com/amiller/smithers-practice) - Reusable Smithers starter kit with research and build-loop workflow templates, a custom monitoring dashboard, and workflow pattern notes.
- [smithers-samples](https://github.com/dennisonbertram/smithers-samples) - Runnable, live-verified sample workflows covering fundamentals, durable resume, human approval, memory, retries, scorers, evals, routing, review, ETL, and fix-until-green loops.
- [smithers-subflow-output-repro](https://github.com/ralfboltshauser/smithers-subflow-output-repro) - Minimal reproduction of a `Subflow mode="childRun"` output issue on smithers-orchestrator 0.25.1: the child run persists its output rows, but the parent `Subflow` receives `undefined` when the child's output schema key is not literally named `output`.
- [Smithers on Vercel Example](https://github.com/smithersai/vercel-example) - Serverless Telegram summary bot example with Vercel Functions, PostgreSQL, Cron, CI gates, and the `.smithers` workflows that built and typecheck the app.
- [smithers-test-workflow](https://github.com/SamuelLHuber/smithers-test-workflow) - Minimal Smithers smoke-test repo with a public `.smithers/workflows/test-echo.tsx` using `@jsxImportSource smithers-orchestrator`, `createSmithers`, and a direct `smithers-orchestrator` dependency.
- [Voltaire Effect Example](https://github.com/evmts/voltaire-effect-example) - Compact example repository showing an older Ralph-style Smithers workflow with phases, agent components, SQLite state, and `.smithers` execution logs.

## Integrations and Benchmarks

- [elizaOS Smithers benchmark adapter](https://github.com/elizaOS/eliza/tree/main/packages/benchmarks/smithers-adapter) - Benchmark adapter that lets elizaOS benchmark harnesses run against Smithers as an agent harness.
- [fable-bench](https://github.com/smithersai/fable-bench) - Smithers benchmark measuring when the `claude-fable-5` model alias stays on Fable versus routes to Opus: one eval-row workflow with live scorers and a saved report, plus a `<Parallel>` fan-out/fan-in suite workflow aggregating model usage, scorer rows, and downgrade rate.
- [Hermes and Eliza Smithers integration](https://smithers.sh/integrations/hermes) - First-party integration shipped by Smithers rather than third-party adoption: `smithers hermes` installs a Smithers-authored plugin, gateway hook, and MCP server into a local Hermes install (slash commands, status injection, approval buttons), and a `HermesCliAgent` lets a Smithers `Task` drive Hermes back. The plugin source lives in the Smithers repo; `NousResearch/hermes-agent` itself carries no Smithers code, so treat this as a supported agent runtime, not an adopter project.
- [Pi Smithers extension](https://github.com/bafflestack/pi-smithers-extension) - Pi (pi.dev) package that launches existing input-free Smithers workflows and observes detached runs, waking an idle Pi session for approval requests, human requests, terminal outcomes, and observer degradation without watch-command or sleep polling.
- [smithers-nanocodex](https://github.com/N0xMare/smithers-nanocodex) - One-shot native bridge between Smithers and stock Nanocodex (Rust): a Smithers `NanocodexAgent` adapter spawns a Bubblewrap-contained bridge process per `generate()` call that runs one normal Nanocodex model/tool loop and returns the final answer plus a resumable session snapshot into a durable Smithers checkpoint.
- [Trellis](https://github.com/smithersai/trellis) - Optimization lab for Smithers' `Trellis` component, first targeting ARC-AGI-3: pins the official evaluator as a submodule, exposes Trellis as an OpenAI-compatible model endpoint, and produces official scorecards with statistical intervals over sampled benchmark runs.

## Embedded Workflows

These projects are not primarily Smithers products, but have public Smithers workflows or workflow experiments worth studying.

- [Agent CAPTCHA](https://github.com/ClementWalter/agent-captcha) - Agent-only posting protocol with cryptographic receipts; its public `.smithers` includes an unattended vulnerability-hunt-and-harden Ralph loop (sandboxed finder, live-prod canary, bounded AI repair with hard revert, auto-redeploy) that shipped real security fixes to the project's own deployment.
- [agent-session-search](https://github.com/benvenker/agent-session-search) - Local MCP server and CLI for searching coding-agent session history, with a 39-workflow Smithers dev-ops pack covering planning, implementation, review, tickets, evals, and a watchdog that monitors its own Smithers runs.
- [claude-p](https://github.com/smithersai/claude-p) - Educational drop-in replacement for `claude -p` that drives Claude Code through an in-process zmux PTY session; the README states it was built using the Smithers self-improving harness.
- [DAML Tools](https://github.com/stevennevins/daml-tools) - Rust/Daml tooling workspace running the full Smithers seeded pack (34 workflows) plus four custom Rust-crate-quality workflows, including a `monitor-smithers` watchdog over its own run fleet and a five-engine agent pool (Claude Code, Codex, Cursor, OpenCode, Antigravity).
- [distillery](https://github.com/TinyCloudLabs/artifactory) - Transcript-to-artifact system with Smithers workflows for staged rich-media smoke tests, agent runs, feed orchestration, and report generation.
- [incur-go](https://github.com/smithersai/incur-go) - Go framework for agent-friendly CLIs with a public `.smithers` workflow pack for implementation, review, test-first, ticket, and PR-description loops.
- [labor.fun expense workflow](https://github.com/BreadchainCoop/labor.fun/blob/main/orchestration/workflows/expense.tsx) - Example of Smithers as a long-lived, human-in-the-loop state machine for expense approval and reimbursement.
- [my-mac-setup](https://github.com/Seigiard/my-mac-setup) - Cross-platform chezmoi dotfiles whose `.smithers` package runs a durable verify-doc, work, verify-code pipeline with dual Claude/OpenCode review legs, provenance-bound (`ctx.prove`/`bind`) gates, post-approval re-scan, and a custom `se` CLI.
- [pdf-to-md Smithers build workflow](https://github.com/ClementWalter/pdf-to-md/tree/main/scripts/smithers-build) - PDF-to-Markdown service built with a dedicated Smithers loop for implementation, tests, review, final review, pass tracking, and persistent workflow state.
- [prettymux](https://github.com/patcito/prettymux) - Native Linux terminal multiplexer (GTK4/libghostty) whose maintainer runs the entire dev loop through Smithers: a reusable implement/validate/review `ValidationLoop`, `Worktree`-based parallel ticket fan-out with agent merge, and Memory-backed incremental feature enumeration across 16 workflows and 4 pooled agents (Claude/Codex/Gemini/Pi).
- [Smithers Terminal fork workflow](https://github.com/roninjin10/smithers-terminal/blob/main/.smithers/main.tsx) - Ghostty fork experiment driven by a Smithers workflow that coordinates phased implementation and review of terminal-agent functionality.
- [smithers-tests](https://github.com/evmts/smithers-tests) - Compact Voltaire release-testing workflow that uses Smithers phases and parallel agents to fan out test work across Git worktrees.
- [Tevm](https://github.com/evmts/tevm-monorepo) - JavaScript-native Ethereum runtime with seeded `.smithers` workflows for implementation, research, review, tickets, and validation loops inside a large production monorepo.

## Research Notes

This first cut was assembled from:

- Smithers ecosystem docs.
- Smithers Workflow Directory.
- Web search for Smithers projects.
- NPM registry search for Smithers packages and package-discovery surfaces.
- MCP and agent marketplace search, including Glama and MCP Market.
- Web and social search for public Smithers workflow mentions outside GitHub.
- Authenticated GitHub repo and code search for `smithers-orchestrator`, `github:evmts/smithers`, `createSmithers`, `@jsxImportSource smithers-orchestrator`, `.smithers/workflows`, and public Smithers workflow references.

The 2026-07-27 sweep merged four discovery channels (this list, GitHub repo and code search, the npm registry, and web/social search) into a single registry of 76 projects, then cloned and read 30 external projects line by line to verify each listing against current source rather than against its README.

The 2026-08-09 sweep re-ran all four discovery channels (authenticated GitHub code and repo search, the npm registry, the Smithers Workflow Directory search API, and web/social search) against the 2026-07-27 registry and verified every new candidate at file level. The headline change since the last census is the npm rename: `smithers-orchestrator` is frozen at 0.32.0 and `smthrs` (0.33.x) plus the `@smthrs/*` scope are the current names, so both names are now search targets; `bb-smithers-workflows` is the first confirmed third-party `smthrs` adopter. Note that authenticated `gh search code` empirically indexes only repositories accessible to the authenticating account, so public-repo discovery leans on `gh search repos` plus direct content verification. `SocketDev/socket-cli`, a former user, removed its smithers-orchestrator fleet installer on 2026-08-07 and no longer contains Smithers code.

Good candidates should be public, directly use Smithers, and have enough readable context that a newcomer can understand why the project is useful. Authenticated GitHub search can surface private repositories and name-adjacent projects; those should be filtered out unless the public repo itself shows clear Smithers evidence. The 2026-07-02 sweep confirmed saturation: authenticated `gh search code` for `smithers-orchestrator` and `@jsxImportSource smithers-orchestrator` surfaced only already-listed public repos plus three private ones (`evmts/mvp`, `roninjin10/dawn`, `smithersai/plue`) that were excluded for lacking public evidence.

## Contributing

Additions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a PR.
