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
2. The power reads your project files to understand the current state
3. It determines which phases apply and presents a plan for confirmation
4. Each phase uses the SOP retrieval tool to get and follow AWS Amplify's official SOPs
5. You get a working full-stack app with best practices baked in

### Phases

| Phase | Description | SOP |
|-------|-------------|-----|
| 1: Backend | Create/modify Amplify backend resources | amplify-backend-implementation |
| 2: Sandbox | Deploy to sandbox for testing | amplify-deployment-guide |
| 3: Frontend | Connect frontend to Amplify backend | amplify-frontend-integration |
| 4: Testing | Local verification (user testing) | - |
| 5: Production | Deploy to production | amplify-deployment-guide |

### Common Patterns

- **New full-stack app**: Phase 1 → 2 → 3 → 4 → 5
- **Add feature to existing backend**: Phase 1 → 2
- **Redeploy after changes**: Phase 2 only
- **Connect existing frontend**: Phase 3 → 4
- **Deploy to production**: Phase 5 only

## MCP Tools

This power uses the AWS MCP server. The steering file references tools abstractly:

- **SOP retrieval tool** - Gets step-by-step execution plans
- **Documentation tools** - Search and read Amplify docs

## License

Apache-2.0
