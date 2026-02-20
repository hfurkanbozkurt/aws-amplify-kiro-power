# AWS Amplify Kiro Power

A [Kiro](https://kiro.dev) power for building full-stack applications with AWS Amplify Gen 2.

## What is this?

This power provides guided workflows for Kiro (AI-powered IDE) to help you build full-stack apps using AWS Amplify Gen 2's TypeScript code-first approach.

## Features

- **Backend**: Auth, data models, storage, Lambda functions, AI/ML integration
- **Deployment**: Sandbox and production environments
- **Frontend**: React, Next.js, Vue, Nuxt, Angular, React Native, Flutter, Swift
- **SOP-driven**: Uses AWS Amplify's official Standard Operating Procedures

## Installation

1. Click on the **Kiro Powers** icon (lightning bolt) in the right sidebar
2. Click **Add Custom Power**
3. Select **GitHub** as the source
4. Paste this URL: `https://github.com/hfurkanbozkurt/aws-amplify-kiro-power`
5. Click **Add Power**

## Prerequisites

- Node.js 18.x or later
- AWS credentials configured (`aws configure` or `aws sso login`)
- npm available

## How it works

1. Describe what you want to build
2. The power validates prerequisites and reads your project files
3. It determines which phases apply and presents a plan for confirmation
4. You confirm, and the power executes one phase at a time
5. After each phase, it stops and waits for your confirmation before proceeding
6. Each phase uses the SOP retrieval tool to get and follow AWS Amplify's official SOPs

### Phases

| Phase | Description | SOP |
|-------|-------------|-----|
| 1: Backend | Create/modify Amplify backend resources | amplify-backend-implementation |
| 2: Sandbox | Deploy to sandbox for testing | amplify-deployment-guide |
| 3: Frontend & Test | Connect frontend + local verification | amplify-frontend-integration |
| 4: Production | Deploy to production | amplify-deployment-guide |

### Common Patterns

- **New full-stack app**: Phase 1 -> 2 -> 3 -> 4
- **Add feature to existing backend**: Phase 1 -> 2
- **Redeploy after changes**: Phase 2 only
- **Connect existing frontend**: Phase 3 only
- **Deploy to production**: Phase 4 only

### Architecture

The power uses split steering files to enforce user confirmation between phases:

```
POWER.md                          -> Entry point, maps to orchestrator only
steering/
  amplify-workflow.md             -> Orchestrator: prereqs, planning, dispatches to phases
  phase1-backend.md               -> Phase 1: Backend (calls backend SOP)
  phase2-sandbox.md               -> Phase 2: Sandbox (calls deployment SOP)
  phase3-frontend.md              -> Phase 3: Frontend + Testing (calls frontend SOP)
  phase4-production.md            -> Phase 4: Production (calls deployment SOP)
  amplify-deploy.md               -> Shared deployment reference
```

The orchestrator loads only the first phase's steering file. Each phase file ends with a hard stop and confirmation question. When the user confirms, the orchestrator dispatches the next phase.

## MCP Tools

This power uses the AWS MCP server. The steering file references tools abstractly:

- **SOP retrieval tool** - Gets step-by-step execution plans
- **Documentation tools** - Search and read Amplify docs

## License

Apache-2.0
