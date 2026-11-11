# 03 — Data & Storage Architecture

## Purpose

Choose storage according to access patterns, consistency, retention, and recovery needs—not popularity or habit.

## Data access layer

Application services, admin tools, reporting, and background workers should use a deliberate data-access boundary. This may include repositories, an ORM/query layer, transaction manager, migrations, and connection pooling.

## Storage options

### Relational database
Useful for structured entities and relationships such as users, roles, orders, billing, and inventory. Design constraints and indexes around correctness and query patterns.

### Document or key-value store
May suit flexible records, sessions, configuration, or event payloads when the access pattern justifies it. Do not add a second database without a clear requirement and ownership plan.

### Cache
Can accelerate hot reads or computed results. Define TTLs and invalidation behavior. A cache should not accidentally become the only source of truth for important records.

### Object storage
Suitable for uploads, images, documents, and exports. Consider signed URLs, access control, lifecycle rules, malware/content checks where relevant, and retention.

### Search index
Supports full-text search, facets, and relevance. The primary database generally remains the source of truth; plan how the index is updated and rebuilt.

### Events and queues
Support asynchronous jobs and delivery retries. An outbox pattern may be appropriate when database changes and event publication must stay coordinated. Define dead-letter handling.

### Analytics and warehouse
Can support aggregates, product analytics, and business intelligence. Design a privacy-aware event pipeline and avoid collecting unnecessary personal data.

## Backup and recovery

Automate backups, consider point-in-time recovery, and perform restore drills. Define Recovery Point Objective (RPO) and Recovery Time Objective (RTO) based on business impact; do not invent targets without stakeholder agreement.

## Data governance

Classify data, minimize collection, define retention and deletion, encrypt appropriately, maintain access logs, and consider residency requirements.

## Design checklist

- What is the source of truth for each entity?
- What consistency guarantees are required?
- Which queries need indexes?
- How are schema migrations reviewed and rolled back?
- How are uploads authorized and retained?
- How are backups restored and tested?
- How are deletion and retention requests handled?
