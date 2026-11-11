# 04 — Security Architecture

## Purpose

Security is a cross-cutting property, not a single feature or final checklist.

## Attack surface

Review browser, APIs, admin interfaces, integrations, uploads, infrastructure, and the developer pipeline. Identify trust boundaries and threat scenarios.

## Identity

Registration, risk-based MFA, password hashing, session lifecycle, and account recovery should be designed together. Use established, maintained identity mechanisms rather than inventing cryptography.

## Access control

Apply RBAC or ABAC where suitable, least privilege, tenant isolation, server-side checks, and admin separation. Test authorization boundaries directly, including cross-user and cross-tenant access.

## Application defense

Validate inputs, encode outputs, and defend against injection. Consider CSRF, XSS, and SSRF controls according to the application's architecture. Treat uploaded files and external payloads as untrusted.

## Edge and network

Use TLS, suitable WAF/DDoS controls, rate limits, secure headers, and network segmentation where appropriate. These controls complement—not replace—secure application code.

## Data protection

Encrypt data in transit and at rest where appropriate. Use secrets management, key rotation, data minimization, and access controls. Never commit secrets to source control.

## Supply chain

Use dependency scanning, lockfiles, SBOMs, signed builds where practical, code review, and CI secret scanning.

## Detection, response, and resilience

Collect security logs, configure anomaly alerts, maintain incident playbooks and audit trails, and define vulnerability handling. Backups, restore tests, disaster recovery, incident communication, and rollback are part of resilience.

## Continuous verification

Threat-model important flows. Map controls to OWASP ASVS or OWASP Top 10 where useful. Use SAST, DAST, dependency audits, and penetration testing proportionate to risk.

> A security scanner's green result is not proof of security. Define threat assumptions, test authorization boundaries, and review high-risk flows manually.
