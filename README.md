# Compliance OS

> AI-powered GRC platform that turns live cybersecurity telemetry into real-time audit evidence, automated control testing, and threat-informed risk intelligence — replacing the manual, screenshot-based compliance workflows that cost enterprises thousands of hours per year.

---

## Live Demo

**https://rumpers.github.io/compliance-os/**

Interactive mockups hosted on GitHub Pages — open in any browser, navigation between all screens works. The fastest way to understand what this is.

---

## The Problem

Enterprises run a major cybersecurity platform on one side and an enterprise GRC platform on the other. Two systems that should be deeply connected, share nothing.

The **security team** has real-time visibility into every threat, vulnerability, and endpoint in the organization. The **audit team** needs evidence that controls are working — and gets it by manually requesting CSV exports from the security team, waiting days, uploading stale screenshots, and repeating the cycle for every control, every audit, every quarter.

Meanwhile, the risk register is updated quarterly by human opinion. The cybersecurity platform knows a ransomware campaign is actively targeting your industry right now — that intelligence never reaches the risk manager.

**There is no live integration between the two systems. None.**

---

## The Solution

Compliance OS is the **security-telemetry intelligence layer that bridges any major cybersecurity platform to any major enterprise GRC platform**, with a standalone GRC layer underneath for enterprises without one.

- **Bridge mode (primary)** — For enterprises already on an enterprise GRC platform, evidence flows directly into their existing control tests. Customers keep their GRC platform, contracts, training, and workpaper conventions. We add the part that hurts.
- **Standalone (fallback)** — For enterprises without a GRC platform, Compliance OS is a full GRC platform on its own — useful both as a greenfield deployment and as a rip-and-replace target for GRC customers facing PE-driven price hikes at renewal.

What both modes deliver:
- **Automated evidence collection** — security-platform data flows directly into control tests. What took 3 days takes 90 seconds.
- **AI interpretation** — Claude reads raw security telemetry and produces auditor-ready compliance narratives mapped to specific control IDs.
- **Live risk register** — Risk scores update automatically when the cybersecurity platform detects significant events. No more quarterly opinion updates.
- **Closed remediation loop** — Findings auto-created from failed controls, tracked through to security-platform-confirmed resolution.
- **Audit-grade evidence chain** — every artifact carries source, query, timestamp, AI prompt + model version, and re-performance hook. Defensible under PCAOB AS 1105 / 1215.

---

## Documents

| Document | Description |
|---|---|
| [PITCH_DECK.md](./PITCH_DECK.md) | 16-slide investor and partner pitch + appendix — validation signal, problem, three buyer lenses, why now, solution, demo, product, competition, native-build threats (CrowdStrike + Workiva), market, business model, GTM, acquisition thesis, ask |
| [PRODUCT_SPEC.md](./PRODUCT_SPEC.md) | Full PRD — target users, use cases, audit standards alignment (PCAOB / AICPA / IAASB / ISO), feature list (MVP → V2), API spec, UI requirements, success metrics, risks, open questions |
| [ARCHITECTURE.md](./ARCHITECTURE.md) | Tech stack, project structure, data flow, setup instructions |

---

## Why Now (2025–2026)

The regulatory and incident environment that makes this product necessary did not exist three years ago:

- **SEC Cybersecurity Disclosure Rule** — 4-business-day Item 1.05 8-K (effective Dec 2023)
- **DORA** — continuous ICT risk controls live for ~22,000 EU financial entities (Jan 17, 2025)
- **NIS2** — board-level personal liability across EU (Oct 2024 transposition)
- **CMMC 2.0** — Final Rule published Oct 15, 2024
- **NIST CSF 2.0** — adds GOVERN function (Feb 2024)
- **PCI-DSS v4.0.1** — full enforcement Mar 31, 2025
- **EU AI Act** — phased application through 2026
- **Change Healthcare ransomware** (Feb 2024) and **Snowflake credential incidents** (May–Jul 2024) — reframed third-party risk for every board
- **Major EDR-vendor outage** (Jul 19, 2024) — single faulty content update from a leading EDR vendor grounded ~8.5M endpoints globally; created the precedent question of who is liable for security-vendor reliability, and how it is evidenced
- **SolarWinds CISO action** (Oct 2023; securities-fraud claim survived motion to dismiss Jul 2024) — CISO is now a discloseable officer with personal exposure

---

## Screens

| Screen | Description |
|---|---|
| [Dashboard](./mockups/dashboard.html) | Compliance posture score, framework breakdown, live activity feed |
| [Controls](./mockups/controls.html) | All controls across all frameworks with real-time status |
| [Evidence Detail](./mockups/evidence.html) | AI-generated evidence with raw data, audit trail, GRC-platform sync status |
| [**Live Risk Register**](./mockups/risks.html) | **Event-driven risk register replacing the quarterly assessment — heatmap, top risks, full provenance chain on the most recent auto-update** |
| [Integrations](./mockups/integrations.html) | Cybersecurity-platform connection, GRC-platform connector, sync logs |

> Open any HTML file directly in a browser — navigation links between all screens work.

---

## How It Works

```
Cybersecurity platform API (EDR / VM / detection)
        ↓
  Connector Layer (auth, retry, pagination)
        ↓
  Collector Layer (agent coverage, vulnerabilities, detections)
        ↓
  AI Interpretation Layer (Claude)
  → maps raw data to compliance control language
  → generates auditor-ready evidence summaries
  → determines PASS / FAIL / EXCEPTION per control
        ↓
  Control Mapping Engine
  → routes evidence to correct controls by framework
        ↓
  ┌─────────────────────────────────────┐
  │  Compliance OS GRC Platform         │
  │  Controls · Evidence · Risks ·      │
  │  Findings · Frameworks · Reports    │
  └─────────────────────────────────────┘
        ↓ (optional)
  GRC-platform Connector
  → pushes formatted evidence to existing control tests in customer's GRC tenant
```

---

## Frameworks Supported

**MVP (V1.0)**: SOC 2 · NIST CSF 2.0 · PCI-DSS v4.0.1 · HIPAA · ISO 27001:2022

**Roadmap**: CMMC 2.0 *(Final Rule published Oct 15, 2024 — phased contract incorporation 2025–2028)* · DORA *(EU, live since Jan 17, 2025)* · NIS2 *(EU)* · NYDFS Part 500 · UK Cyber Essentials Plus

---

## Connectors

**Data Sources (cybersecurity platforms)**
- One major EDR vendor *(required for MVP — agent coverage, vulnerability data, detections; first-vendor-supported announced separately)*
- Additional EDR vendors *(V2.0 — multi-vendor support, prioritized post-Jul 2024 industry-wide vendor-concentration discussions)*
- Identity provider *(roadmap)*
- Cloud activity logs *(roadmap)*

**GRC Destinations**
- Leading enterprise GRC platform *(optional bridge mode — push evidence into customer's existing tenant)*
- Additional enterprise GRC platforms *(roadmap)*
- Mid-market GRC platforms *(roadmap)*

---

## Tech Stack

| Layer | Technology | Version (as of 2026) |
|---|---|---|
| Frontend | Next.js (App Router) + React + TypeScript | Next.js 15, React 19 |
| UI | Tailwind CSS + shadcn/ui | Tailwind v4 |
| Database | PostgreSQL + Prisma ORM | Postgres 16, Prisma 5.x |
| AI | Anthropic Claude API | `claude-opus-4-7` (interpretation), `claude-haiku-4-5` (UI summarization), prompt caching enabled |
| Auth | Auth.js (formerly NextAuth.js) | v5 |
| Jobs | node-cron → BullMQ (V1.5) | — |

---

## Acquisition Targets

Built to be acquired by buyers in five adjacent positions. Each has independent, current strategic motivation. Multiple credible buyers in adjacent positions = auction dynamic at exit.

- **Category-leading enterprise GRC platform** *(primary target — now PE-backed since May 2024 at reported ~$3B; PE hold of 5–7 years places exit window ~2028–2031; bridge-mode positioning lands us on the M&A consideration list as a bolt-on)*
- **Public-company AI-GRC challenger** — launched its AI-Powered GRC Platform Mar 9, 2026; acquired an AI-workpaper-automation startup as the precedent that this buyer pays for category-specific AI audit tooling; 70+ connectors but none for security telemetry
- **Major EDR / cybersecurity-platform vendors** — active consolidators extending their platforms into the CFO / CAE / CCO budget through bolt-on acquisitions in adjacent security categories
- **Enterprise IRM / ITSM platforms** — accelerate their security-evidence story without internal build
- **CNAPP / DSPM platforms** — need a framework-mapping engine to enter GRC

Specific named buyers, recent M&A comparables, and timeline pressure are detailed in the Acquisition Thesis section of the pitch deck.

---

## Status

Pre-MVP — architecture, planning, and mockups complete. Build starting.
