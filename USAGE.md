# Usage Guide

This guide explains how to use the templates in this repository when handing over an internal admin console or operational tool.

## Recommended Order

Use the templates in this order:

1. `HANDOVER_TEMPLATE.md`
2. `ADR_TEMPLATE.md`
3. `TROUBLESHOOTING_TEMPLATE.md`
4. `DEPLOYMENT_GUIDE_TEMPLATE.md`
5. `ANONYMIZATION_CHECKLIST.md`

## 1. Start With Handover

Create a handover document before writing detailed troubleshooting or deployment notes.

The handover document should answer:

- What does this system do?
- Who uses it?
- What are the main operational workflows?
- What data sources does it depend on?
- Where is it deployed?
- What should a new maintainer avoid changing casually?

The goal is not to explain every line of code. The goal is to give the next maintainer an operational map.

## 2. Record Important Decisions As ADRs

Use `ADR_TEMPLATE.md` whenever the system has a decision that may look surprising later.

Good ADR candidates:

- Splitting one admin console into multiple deployments
- Choosing static hosting for a React SPA
- Using object storage for generated JSON snapshots
- Putting API Gateway in front of serverless functions
- Moving long-running work into a background worker

Each ADR should include the context, rejected options, accepted trade-offs, and revisit conditions.

## 3. Write Troubleshooting Notes From Symptoms

Troubleshooting docs should start from observable symptoms, not internal implementation details.

Examples:

- The UI shows stale data.
- A report stays in progress.
- The browser shows a CORS error.
- A deployment succeeded but the page still shows old assets.

For each symptom, document the first place to check, the likely cause, and the safest recovery action.

## 4. Keep Deployment Notes Operational

A deployment guide should not be only a list of commands.

It should also explain:

- What changes are included in the deployment
- What must be checked before deployment
- What must be verified after deployment
- How to roll back or recover
- Which caches or generated assets may need refresh

## 5. Anonymize Before Publishing

Before turning internal documentation into public writing, use `ANONYMIZATION_CHECKLIST.md`.

Remove or replace:

- Real company names
- Production domains
- Bucket names
- API IDs
- Distribution IDs
- Database hosts
- Cookie names
- Customer or partner names
- Exact traffic, cost, or operational numbers when not essential

Public writing should preserve the structure, reasoning, and trade-offs, not the internal identifiers.

## Maintenance Rhythm

For active systems, review these documents when:

- A deployment process changes
- A new external dependency is added
- A recurring incident happens
- Ownership changes
- A decision becomes hard to explain without context

