# 05 — Delivery, Infrastructure & Operations

## Purpose

Delivery should be repeatable, observable, and recoverable from a developer's machine through production.

## Source control

Use Git, sensible branch protections, pull requests, code owners where useful, and version tags. Keep secrets and generated artifacts out of source control.

## CI pipeline

A typical pipeline may run linting, type checks, unit and integration tests, builds, and security scans. Make failures visible and actionable.

## Build artifact

Prefer immutable, identifiable bundles or images. Track dependency locks, SBOMs where appropriate, and version metadata.

## CD and release

Define approval gates, migration review, rollout strategy, rollback, and release notes. A deployment is not complete merely because the build succeeded.

## Environments

- **Development:** local environment, mock services, seed data, developer documentation.
- **Staging:** production-like configuration, safe test data, acceptance tests, release validation.
- **Production:** hosting/runtime, database, object storage, CDN, and DNS as required.

Keep environment configuration deliberate and avoid copying production secrets into development.

## Infrastructure as code

Use repeatable infrastructure definitions where the complexity and operational model justify them. Manage secrets through references to a secrets system, not committed plaintext.

## Observability

Collect structured logs and traces with request IDs. Monitor latency, errors, traffic, saturation, and uptime. Alerts should have an owner and an action.

## Backup and recovery

Use database snapshots and object versioning where appropriate. Run restore drills and agree RPO/RTO with stakeholders.

## Operations

Define an on-call or responsible owner, incident runbooks, status communication, and postmortems.

## Release gate

Do not deploy until tests pass, migrations are reviewed, secrets are configured, backups are healthy, monitoring is active, and rollback is understood.
