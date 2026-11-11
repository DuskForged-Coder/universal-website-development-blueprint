# 07 — How to Use This Blueprint

## A practical adaptation method

### 1. Discover

Identify users, business outcomes, workflows, data types, integrations, constraints, and compliance needs. Record non-goals and success measures.

### 2. Classify

Mark each module as:

- **Required** — needed for a defined product requirement.
- **Optional** — useful under a stated condition; record the reason.
- **Not Needed** — deliberately excluded for this product.

Do not include a technology or service merely because it appears in the diagram.

### 3. Design

Choose architecture style, trust boundaries, data model, API contracts, failure modes, and deployment topology. Document important trade-offs and operational ownership.

### 4. Build

Implement vertical slices:

`user journey → UI → API → data → tests → telemetry`

Deliver a working, testable path before expanding into unrelated modules.

### 5. Verify

Test functionality, security, accessibility, performance, recovery, privacy, and operational readiness. Match test depth to risk.

### 6. Operate and evolve

Monitor real usage, incidents, and cost. Refactor or scale only when evidence justifies it.

## Scaling principle

Complexity is earned by requirements.

A simple brochure site may need static pages and a contact form. A multi-tenant SaaS may need queues, audit trails, tenant isolation, observability, and formal recovery targets. Neither architecture is universally correct.

## Architecture decision record template

Use one record for each significant decision.

```text
# ADR-NNN: <decision title>

Status: Proposed | Accepted | Superseded
Date:
Owners:

## Context
What requirement or problem prompted this decision?

## Decision
What are we choosing?

## Alternatives considered
What other options were evaluated?

## Consequences
What benefits, trade-offs, risks, and operational costs follow?

## Verification
How will we test that this decision works as intended?
```

## Project readiness review

Before release, confirm:

- Requirements and success metrics are documented.
- Modules are classified and optional choices justified.
- Sensitive operations have server-side authorization.
- Inputs, uploads, and webhooks are validated.
- Secrets are protected.
- Retries are safe and critical actions are idempotent.
- Tests cover important behavior and risk.
- Accessibility, performance, and privacy are reviewed.
- Monitoring and alert ownership are clear.
- Backups and restore procedures are tested.
- Release and rollback procedures are understood.
