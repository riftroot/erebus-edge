# Erebus Edge — Operational Surface

This inventory represents the production endpoints, workers, durable objects, scheduled crons, and task handlers running across the Erebus Edge mesh. The system operates roughly 100 HTTP endpoints across 35+ workers, six Durable Objects, fifteen scheduled crons, and forty-plus task handlers — five categories that map directly to the five-layer architecture.

## Hostile Network Enablement — 16 surfaces

- `POST /v1/admin/secrets/status` — List vault keys
- `POST /webhooks/github` — GitHub push receiver
- `env CF_ACCESS_CLIENT_ID / …SECRET` — CF Access service-to-service

## Task Lifecycle & Execution — 39 surfaces

- `POST /v1/tasks` — Create task
- `POST /v1/worker/poll` — Worker poll for work
- `POST /v1/dispatch/microvm` — Allocate microVM

## Learning & Intelligence — 36 surfaces

- `POST /v1/llm/chat` — Chat endpoint
- `POST /v1/admin/bandit/status` — Bandit state snapshot
- `POST /v1/docs/semantic-search` — Embedding-based query

## Event Sourcing & Observability — 24 surfaces

- `POST /v1/events` — Event ingest
- `DO D1 (primary database)` — Reward/cost ledger
- `cron 0 */6 * * *` — Drift-detection cron

## Operator Console — 25 surfaces

- `POST /v1/admin/attention/recycle` — Re-enqueue stuck tasks
- `POST /v1/admin/swarm/status` — Fleet health snapshot
- `POST /v1/admin/arch/ingest` — Ingest repo architecture

---

Inventory current as of 2026-04. Public-facing summary; implementation details proprietary.