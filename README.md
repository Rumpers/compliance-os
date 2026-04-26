# Compliance OS

> AI-powered GRC platform that turns live CrowdStrike security telemetry into real-time audit evidence, automated control testing, and threat-informed risk intelligence — replacing the manual, screenshot-based compliance workflows that cost enterprises thousands of hours per year.

---

## The Problem

Companies using CrowdStrike and AuditBoard operate two systems that should be deeply connected but share nothing.

The **security team** has real-time visibility into every threat, vulnerability, and endpoint in the organization. The **audit team** needs evidence that controls are working — and gets it by manually requesting CSV exports from the security team, waiting days, uploading stale screenshots, and repeating the cycle for every control, every audit, every quarter.

Meanwhile, the risk register is updated quarterly by human opinion. CrowdStrike knows a ransomware campaign is actively targeting your industry right now — that intelligence never reaches the risk manager.

**There is no integration between CrowdStrike and AuditBoard. None.**

---

## The Solution

Compliance OS is a full GRC platform with an optional AuditBoard connector:

- **Automated evidence collection** — CrowdStrike data flows directly into control tests. What took 3 days takes 90 seconds.
- **AI interpretation** — Claude reads raw security telemetry and produces auditor-ready compliance narratives mapped to specific control IDs.
- **Live risk register** — Risk scores update automatically when CrowdStrike detects significant events. No more quarterly opinion updates.
- **Closed remediation loop** — Findings auto-created from failed controls, tracked through to CrowdStrike-confirmed resolution.
- **AuditBoard connector** — For customers who already use AuditBoard, evidence is pushed automatically. Keep your existing platform, eliminate the manual work.

---

## Screens

| Screen | Description |
|---|---|
| [Dashboard](./mockups/dashboard.html) | Compliance posture score, framework breakdown, live activity feed |
| [Controls](./mockups/controls.html) | All controls across all frameworks with real-time status |
| [Evidence Detail](./mockups/evidence.html) | AI-generated evidence with raw data, audit trail, AuditBoard sync status |
| [Integrations](./mockups/integrations.html) | CrowdStrike connection, AuditBoard connector, sync logs |

> Open any HTML file directly in a browser — navigation links between all screens work.

---

## Documents

| Document | Description |
|---|---|
| [PITCH_DECK.md](./PITCH_DECK.md) | 13-slide investor and partner pitch — problem, solution, market, GTM, acquisition thesis |
| [PRODUCT_SPEC.md](./PRODUCT_SPEC.md) | Full PRD — use cases, feature list (MVP → V2), API spec, UI requirements, success metrics |
| [ARCHITECTURE.md](./ARCHITECTURE.md) | Tech stack, project structure, data flow, setup instructions |

---

## How It Works

```
CrowdStrike Falcon API
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
  AuditBoard Connector
  → pushes formatted evidence to existing AuditBoard control tests
```

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

## Frameworks Supported

**MVP (V1.0)**: SOC 2 · NIST CSF 2.0 · PCI-DSS v4.0.1 · HIPAA · ISO 27001:2022

**Roadmap**: CMMC 2.0 *(Final Rule published Oct 15, 2024 — phased contract incorporation 2025–2028)* · DORA *(EU, live since Jan 17, 2025)* · NIS2 *(EU)* · NYDFS Part 500 · UK Cyber Essentials Plus

---

## Connectors

**Data Sources**
- CrowdStrike Falcon *(required for MVP — agent coverage, Spotlight vulnerabilities, detections)*
- Microsoft Defender for Endpoint *(V2.0 — multi-EDR support post-Jul 2024 Falcon outage)*
- SentinelOne Singularity *(V2.0)*
- Okta *(roadmap — identity & access)*
- AWS CloudTrail *(roadmap — cloud activity)*

**GRC Destinations**
- AuditBoard *(optional — push evidence into existing tenant)*
- ServiceNow IRM *(roadmap)*
- Hyperproof / LogicGate *(roadmap)*

---

## Live Demo

**https://rumpers.github.io/compliance-os/**

Interactive mockups hosted on GitHub Pages — open in any browser, navigation between all screens works.

## Status

Pre-MVP — architecture, planning, and mockups complete. Build starting.

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
- **CrowdStrike Falcon outage** (Jul 19, 2024) — created the precedent question: who is liable for security-vendor reliability, and how is it evidenced
- **SolarWinds CISO action** (Oct 2023; securities-fraud claim survived motion to dismiss Jul 2024) — CISO is now a discloseable officer with personal exposure

---

## Acquisition Targets

Built to be acquired. Strategic buyers in adjacent positions, with recent acquisition activity confirming the playbook:

- **CrowdStrike** — extends Falcon into CFO/CAE budget. Pattern: Adaptive Shield (Nov 2024, ~$300M), Flow Security (Mar 2024, ~$200M), Bionic (Oct 2023, ~$350M), Humio (Feb 2021, ~$400M)
- **AuditBoard (Hg Capital)** — gains real-time security telemetry; Hg's PE thesis is bolt-on M&A (acquired AuditBoard May 2024 at reported ~$3B)
- **ServiceNow** — accelerates IRM security evidence story without internal build
- **Palo Alto Networks** — active consolidator: Talon (Nov 2023, $625M), Dig Security (Nov 2023, ~$400M), QRadar SaaS from IBM (May 2024)
- **SentinelOne** — needs the compliance layer to compete on board-level value; PingSafe (Jan 2024)

Multiple credible buyers in adjacent positions = auction dynamic at exit.
