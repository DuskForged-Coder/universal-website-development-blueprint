# 06 — Integrations & Optional Product Modules

## Purpose

This page is a capability catalogue. Include only the modules the product actually needs.

## Core application

The core usually includes frontend, backend, identity, data, security, and operations. The exact boundaries depend on product requirements.

## Commerce

Possible capabilities include catalogue, cart, checkout, orders, tax, invoices, refunds, and subscriptions. Payment processing introduces security, reconciliation, webhook, and operational requirements.

## Content and publishing

A CMS, pages, blog, media library, drafts, approval workflow, and localization may be useful for content-heavy products.

## Communication and collaboration

Email, SMS, WhatsApp, notifications, chat, and support tickets should be added according to user journeys and consent requirements.

## Analytics and personalization

Events, funnels, dashboards, recommendations, experiments, and consent management require clear data governance and purpose.

## Enterprise capabilities

Multi-tenancy, SSO, audit exports, approvals, policy engines, and SLA workflows are justified by enterprise needs—not automatically required for every application.

## AI and automation (optional)

A model gateway, retrieval, evaluations, human review, safety controls, and cost controls may be relevant. Define data boundaries, reliability expectations, human oversight, and failure behavior.

## Location and search (optional)

Maps, geocoding, full-text search, filters, and geo queries should be included only where product behavior needs them.

## Mobile and PWA (optional)

Installability, offline strategy, push notifications, deep links, and app APIs introduce additional testing and support requirements.

## Integration rules

- Use adapters to isolate vendor-specific details.
- Store credentials server-side in an appropriate secrets system.
- Verify webhook signatures.
- Set timeouts and retry safely.
- Document what data is shared with vendors.
- Provide graceful fallbacks when an integration is unavailable.
- Monitor cost, rate limits, and vendor changes.
