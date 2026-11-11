# 02 — Backend / Application Architecture

## Purpose

The backend handles requests, business rules, authorization, integrations, persistence boundaries, and asynchronous work.

## Request path

Callers may be a web frontend, mobile app, admin console, partner system, or scheduled job. An edge/API gateway can handle TLS termination, routing, request-size limits, rate limits, CORS, and request IDs.

## API interface

Choose REST, GraphQL, or RPC based on actual client and domain needs. Define versioning, schema validation, pagination, and consistent error responses. Avoid exposing internal implementation details in errors.

## Identity and authorization

Verify sessions or tokens. Apply roles and permissions, tenant scope, and policy checks. Sensitive operations must be authorized on the server for every request; hiding a button is not an access-control mechanism.

## Application and domain services

Represent use cases, business rules, workflows, transaction boundaries, and domain events in intentional service boundaries. Keep business rules out of transport handlers where possible.

## Asynchronous processing

Queues, workers, retries, dead-letter queues, and scheduled tasks can move slow or deferred work out of request handling. Design retried operations to be idempotent. Define retry limits and failure handling.

## Integration adapters

Payment, email, SMS, CRM, webhooks, and external APIs should be isolated behind adapters. Configure timeouts and, where appropriate, circuit breakers. Verify webhook signatures and make webhook processing safe against duplicate delivery.

## Persistence ports

Repositories, transaction boundaries, cache interfaces, and object-storage interfaces help isolate domain logic from storage implementation.

## Observability and testing

Use structured logs, metrics, traces, correlation IDs, alerts, and audit events. Backend testing may include unit, integration, contract, authorization, load, resilience, and migration tests.

## Non-negotiables

- Validate every untrusted input.
- Authorize every sensitive operation server-side.
- Make retried operations idempotent.
- Never expose secrets.
- Define timeouts and failure behavior.
