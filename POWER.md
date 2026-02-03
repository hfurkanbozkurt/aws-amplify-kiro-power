---
name: "aws-amplify"
displayName: "Build full-stack apps with AWS Amplify"
description: "Build and extend full-stack applications with AWS Amplify Gen 2 using type-safe TypeScript, guided workflows, and best practices. Covers adding features to existing Amplify backends, authentication, data models, storage, serverless functions, and AI/ML integration."
keywords: ["amplify", "aws-amplify", "amplify gen 2", "gen2", "fullstack", "full-stack", "lambda", "graphql", "cognito", "sandbox", "backend", "auth", "authentication", "storage", "data model", "react", "nextjs", "next.js", "vue", "nuxt", "angular", "react native", "flutter", "swift", "android", "ios"]
author: "AWS"
---

# AWS Amplify Gen 2

## Overview

Build full-stack applications with AWS Amplify Gen 2 using TypeScript code-first development. This power provides guided workflows for:

- Creating backend resources (auth, data, storage, functions)
- Deploying to sandbox and production environments
- Integrating frontend frameworks (React, Next.js, Vue, Angular, Flutter, Swift)
- Following Amplify Gen 2 best practices

## Getting Started

⚠️ **IMPORTANT: You MUST read and follow the steering file for ANY Amplify work.** Do not improvise or skip the workflow.

**For AI agents helping users build Amplify apps:**

### Step 1: Validate Prerequisites

Run these checks before proceeding:

1. **Node.js 18.x or later**
   ```bash
   node --version
   ```

2. **npm available**
   ```bash
   npm --version
   ```

3. **AWS credentials configured** (CRITICAL)
   ```bash
   AWS_PAGER="" aws sts get-caller-identity
   ```

### Step 2: Handle Missing AWS Credentials

If the AWS credentials check fails, **STOP** and present this message to the user:

```
## ⚠️ AWS Credentials Required

I can't proceed without AWS credentials configured. Please set up your credentials first:

**📚 Setup Guide:** https://docs.amplify.aws/react/start/account-setup/

**Quick options:**
- Run `aws configure` to set up access keys
- Run `aws sso login` if using AWS IAM Identity Center

Once your credentials are configured, **come back and start a new conversation** to continue building with Amplify.
```

**Do NOT proceed with Amplify work until credentials are configured.** The user must restart the conversation after setting up credentials.

### Step 3: Read the Workflow

Once all prerequisites pass, ALWAYS read the workflow steering file:

```
Call action "readSteering" with powerName="aws-amplify", steeringFile="amplify-workflow.md"
```

Follow the workflow completely. It will guide you through:
- Determining which phases apply to the user's request
- Presenting a plan and getting confirmation
- Executing phases: Backend → Sandbox → Frontend → Testing → Production
- Calling the appropriate SOPs for each phase

## Available Steering Files

This power has one steering file:

- **amplify-workflow** - Orchestrated workflow for Amplify Gen 2 development. Coordinates phases: Backend → Sandbox → Frontend → Testing → Production.
