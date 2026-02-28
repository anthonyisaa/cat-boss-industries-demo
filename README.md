# Cat Boss Industries Demo

Cat Boss Industries is a **demo project only**. Its purpose is to help you get up to speed with **Mission Control** by giving you realistic feature/bug/UI work to run through `mc` and `mc-status`.

This repository is **not** Mission Control itself. Use it as the target codebase while Mission Control orchestrates your agents.

## Stack
- Next.js + TypeScript
- Prisma + SQLite
- Vitest
- Playwright

## Local setup
```bash
npm install
npm run db:generate
npm run db:push
npm run db:seed
npm run dev
```

## Mission Control Context
- Mission Control is the orchestrator (`mc`, `mc-status`) used to run parallel agents.
- Cat Boss is the workload for that orchestrator.
- If `mc` is not available on your machine, set up Mission Control first, then return to this repo.

## Demo Paths
### 1) Quick 2-minute dashboard demo
```bash
mc init
mc day start --goals "Quick queue demo;Show needs_input routing;Close all agents"
mc start agent-alpha --goal "Simulate feature lifecycle" 
mc start agent-beta --goal "Simulate bug lifecycle"
mc start agent-gamma --goal "Simulate UI lifecycle"
```
Then run the per-agent scripts from [`missions/quick/README.md`](missions/quick/README.md).

### 2) Full artifact-driven day-in-the-life demo
```bash
mc init
mc day start --goals "Implement PRD-004 escalation flow;Resolve GH-128 blocked-filter regression;Ship DR-011 console redesign"
mc start agent-feature --goal "Implement PRD-004 from docs/prd/PRD-004-incident-escalation.md with tests"
mc start agent-bugfix --goal "Fix GH-128 from docs/issues/GH-128-blocked-filter-refresh.md and add regression coverage"
mc start agent-ui --goal "Execute DR-011 from docs/design/DR-011-ops-console-refresh.md with responsive overhaul"
```
Use [`missions/full/launch.md`](missions/full/launch.md) and the per-agent briefs in `missions/full/`.

## Mission Artifacts
- PRD: [`docs/prd/PRD-004-incident-escalation.md`](docs/prd/PRD-004-incident-escalation.md)
- GitHub issue mirror: [`docs/issues/GH-128-blocked-filter-refresh.md`](docs/issues/GH-128-blocked-filter-refresh.md)
- Design brief: [`docs/design/DR-011-ops-console-refresh.md`](docs/design/DR-011-ops-console-refresh.md)
- Shared decision contract: [`docs/decisions/DEC-002-severity-contract.md`](docs/decisions/DEC-002-severity-contract.md)
