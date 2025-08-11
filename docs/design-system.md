# Lovable, Figma, & Replit Design System

This document defines the foundational design system and core user flows for the enterprise AI development platform that spans the software lifecycle: **Plan → Build → Test → Ship → Operate**. The system supports English (LTR) and Arabic (RTL) and aligns with brand aesthetics supplied separately.

## 1. Global UI Framework

### Language & Directionality
- A global language toggle in the top bar switches between English and Arabic (`العربية`).
- Switching to Arabic mirrors the interface: navigation flows right‑to‑left, menus open leftward, progress indicators and directional icons flip.
- English uses `Inter` or `Montserrat`; Arabic uses `Cairo` or `Tajawal` at slightly larger sizes for readability.
- Inputs accept long Arabic names and support bi‑directional text within a single field.

### Top Bar & Side Navigation
- **Top Bar**: organisation switcher, project/environment pickers (Dev/Staging/Prod), notifications, quick actions (New project, New pipeline run), language toggle.
- **Side Navigation**: Overview, Projects, Pipelines, Prompts, Data, Integrations, QA, Security, Deploy, Observability, Governance, Marketplace, Admin. Items mirror in RTL.

### Responsive Layouts
- Breakpoints for desktop, tablet, and mobile. Navigation collapses into icons or drawers as space reduces.
- RTL flipping applies consistently across breakpoints.

## 2. Overview
- **Organisation Dashboard**: cards showing active projects, release calendar, compliance status, incident alerts, DORA metrics, and cost snapshots (cloud + LLM).
- **Program Board**: Kanban with slices (Plan/Build/Test/Ship) filterable by team, priority, or time frame.
- **Scorecards**: KPI charts for PMs, VP Engineering gates, and CSO risk heatmap. Charts animate according to language direction.

## 3. Projects Workspace
- **Project Dashboard**: latest runs, open risks, environment health, live endpoints, and quick links to backlog, pipelines, artifacts.
- **Backlog & Slices**: roadmap with user stories (Gherkin), acceptance criteria, status.
- **Artifacts**: access PRD.md, ARCHITECTURE.md, OPENAPI.yaml, schema.prisma, SECURITY.md.
- **Decisions & ADRs**: timeline viewer for trade‑offs, approvals, change logs.
- **Team & Roles**: RACI assignments editable per role (PM, TL, FE, BE, AI/ML, DevOps, QA, CSO, VP Eng, Sales Eng).

## 4. Pipelines
- **Run History**: list runs with status, duration, produced artifacts, cost; drill into logs.
- **Pipeline Designer**: drag‑and‑drop canvas of nodes for roles/teams, triggers (Manual, Git push, Cron, Webhook), gates (QA, security scans, performance thresholds), approvals (manual holds). Nodes flip in RTL.
- **Replay & Diff**: compare prompts, outputs, configs between runs.

## 5. Prompts Hub
- **Prompt Templates** grouped by role (Orchestrator, PM, Tech Lead, UI/UX, Frontend, Backend, AI/ML, DevOps, QA, CSO, VP Engineering, Sales Eng) with versioning.
- **Variables & Context**: fields for goal, tech stack, constraints, acceptance criteria, target region; response schema definitions enforce structure.
- **Cost & Latency Benchmarks**: charts comparing models (Claude, GPT‑5, HuggingFace) across cost vs. latency.

## 6. Design Module
- **Design Tokens**: light/dark theme colours, spacing, typography scales, icon sizes. All tokens pass WCAG contrast requirements.
- **Components Library**: specs for cards, forms, tables, modals with state diagrams (default, hover, active, disabled, loading).
- **User Flows & Micro‑interactions**: screen maps for loading, empty, error, success states with mirrored animations for RTL.
- **Export Assets**: Figma exports (fig.json, component inventory) feed frontend scaffolding.

## 7. Frontend (Next.js/TypeScript)
- High‑level routing map of pages, layouts, middleware, API routes.
- State management via React Query or Zustand; caching strategies and performance budgets (p75/p95, CLS/LCP targets).
- Scaffolding hints for automated generation.

## 8. Backend (NestJS + Prisma + Postgres + Redis)
- Domain models via `schema.prisma`, API contracts (OpenAPI paths, DTOs, guards/interceptors).
- Queue plans with BullMQ, real‑time events via WebSockets/SSE, seed datasets for demos/tests.

## 9. Data & AI
- Data sources: Postgres/Supabase, object storage, external APIs.
- Vector store with pgvector schema, chunking policies, embedding providers.
- LLM features: prompt catalogues, tool selection, fallback trees, evaluation harness for accuracy, latency, toxicity, cost.

## 10. DevOps & Deploy
- Environment map (Dev/Staging/Prod), secrets and variables.
- Interactive CI/CD designer (GitHub Actions) with canaries, rollbacks, environment‑specific configs (vercel.json, render.yaml, ci.yml).

## 11. QA & Security
- Dashboards for E2E (Playwright), API (.http), performance (k6), accessibility tests.
- Visualised quality gates and budgets; security scans (OWASP ZAP, Snyk/Dependabot), threat models, data classification, DLP rules, OPA/Rego snippets.

## 12. Observability
- Monitoring dashboards for runtime health (p95 latency, error rates), log/trace filters, cost and usage analytics, incident center with alerts and playbooks.

## 13. Integrations & Marketplace (Phase 2)
- Connectors for Git providers, cloud services, communication platforms, LLM providers, automation flows.
- Marketplace pages for blueprints, prompt packs, and modular features.

## 14. Governance & Compliance (Phase 2)
- Policies, approvals, audit trails, regional flags (KSA/GCC data residency, localisation).

## 15. Admin & Access
- RBAC management (org/project/env scopes), secrets rotation, theme customisation, i18n defaults, audit logs.

## 16. Minimal Viable Slice – Phase 1
Focus designs on:
- Projects + Pipelines + Prompts loop.
- Artifacts & repo sync.
- CI & Deploy.
- QA gates with Slack notifications.
- Lite observability (run logs, p95, basic cost).

## 17. Accessibility & Testing
- WCAG‑compliant colours, keyboard navigation, clear focus states, alt text.
- Use Figma plugins (Stark/Contrast) to verify colour ratios.
- Labels and descriptions are concise and jargon‑free.
- Interactive elements reachable via keyboard with logical tab order.
- Prototype testing with English and Arabic speakers to validate mirroring and text expansion.

## 18. Deliverables
- Layered Figma file containing design system, components, and prototypes with language switch and micro‑interactions.
- This documentation for developers with rationale, accessibility checks, and implementation notes.

---
This document serves as the baseline for implementing the Lovable, Figma, & Replit platform’s user experience.
