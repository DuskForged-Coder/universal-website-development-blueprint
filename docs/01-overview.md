# 00 — Master Blueprint

## Purpose

The Master Blueprint is the system-level map. It connects product definition, client entry points, edge delivery, frontend, backend, data, security, operations, external services, internal tools, and quality governance.

It is deliberately modular: not every website needs every capability.

## 1. Product definition

Before choosing a framework or cloud provider, define:

- Business goals and measurable outcomes
- Target users and their important journeys
- Scope and explicit non-goals
- Data types and sensitivity
- External integrations
- Availability, performance, and recovery expectations
- Compliance obligations, budget, and team constraints
- Success metrics

These decisions shape the architecture.

## 2. Client and edge

Clients may include a desktop browser, mobile browser, Progressive Web App (PWA), or an optional native application.

The edge and delivery layer can include DNS, CDN, Web Application Firewall (WAF), TLS termination, caching, rate limiting, and bot protection. Select controls based on exposure and risk. Do not assume that adding an edge product replaces application-level validation or authorization.

## 3. Application layers

- **Frontend:** user interface, pages, components, routing, state, forms, accessibility, and client-side validation.
- **Backend/application:** API layer, business logic, services, background jobs, integrations, and authorization.
- **Data and storage:** persistence selected by access pattern, consistency, retention, and recovery requirements.

The frontend communicates with backend interfaces. The backend owns business rules and sensitive authorization decisions. Data stores should be accessed through intentional boundaries rather than scattered direct access.

## 4. Cross-cutting capabilities

Security applies across every layer: identity, roles and permissions, secrets, validation, encryption, audit, and threat modelling.

Delivery and operations cover Git, CI/CD, environments, infrastructure, observability, and incident response.

Quality and governance include testing, accessibility, performance, SEO, privacy, documentation, and handover.

## 5. External services and internal tools

External services may include payment providers, email/SMS, CRM, analytics, maps, identity providers, and partner APIs. Admin/internal tools may include a CMS, user management, support console, feature flags, and audit viewer. These are included only when the product needs them.

## Architecture rule

Every module is conditional. Start with the smallest safe architecture that meets requirements; add complexity only when justified.

## Practical review questions

1. Which user journey requires this component?
2. What happens if the component is unavailable?
3. What data crosses its boundary?
4. Who is allowed to invoke it?
5. How will it be tested, monitored, and recovered?
6. What operational cost does it introduce?
