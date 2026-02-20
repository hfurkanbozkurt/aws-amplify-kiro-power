# Amplify Deploy

Deploy an AWS Amplify Gen 2 application to sandbox or production.

## When to Use This Workflow

This file contains shared deployment logic used by Phase 2 (sandbox) and Phase 5 (production).

It is **not** mapped in POWER.md and is **not** invoked directly by the user.
Phase steering files (`phase2-sandbox.md`, `phase5-production.md`) reference this
for context, but each phase file retrieves and follows the SOP itself.

---

## Mapping Deployment Targets to SOP Parameters

The SOP uses the parameter name `deployment_type` with values `sandbox` or `cicd`.
Map caller intent as follows:

- "sandbox", "development", "testing" -> SOP deployment_type: **sandbox**
- "production", "prod", "live", "release", "cicd" -> SOP deployment_type: **cicd**

---

## SOP Reference

The **"amplify-deployment-guide"** SOP must be retrieved using the SOP retrieval
tool from `aws-mcp`.

**All steps in the SOP must be followed** for any type of deployment
(sandbox or production). The SOP contains the latest and most accurate
deployment procedures. Do not improvise or skip steps.

### Critical Rules

1. **Follow the SOP completely** - Do not improvise or skip steps
2. **If you encounter an error:**
   - Fix the immediate issue
   - Return to the SOP and continue from where you left off
   - Do NOT abandon the SOP
3. **If you lose track of where you were:**
   - Retrieve the SOP again
   - Identify which step you completed last
   - Continue from the next step
