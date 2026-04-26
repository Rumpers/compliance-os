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

| Layer | Technology |
|---|---|
| Frontend | Next.js 14 (App Router) + TypeScript |
| UI | Tailwind CSS + shadcn/ui |
| Database | PostgreSQL + Prisma ORM |
| AI | Anthropic Claude API |
| Auth | NextAuth.js |
| Jobs | node-cron (scheduled syncs) |

---

## Frameworks Supported

SOC 2 · NIST CSF · PCI-DSS v4.0 · HIPAA · ISO 27001 · CMMC *(roadmap)*

---

## Connectors

**Data Sources**
- CrowdStrike Falcon *(required)*
- Okta *(roadmap)*
- AWS CloudTrail *(roadmap)*

**GRC Destinations**
- AuditBoard *(optional)*
- ServiceNow GRC *(roadmap)*

---

## Status

Pre-MVP — architecture, planning, and mockups complete. Build starting.

---

## Acquisition Targets

Built to be acquired by CrowdStrike, AuditBoard, ServiceNow, Palo Alto Networks, or SentinelOne — each has a strategic reason to own the compliance intelligence layer that bridges security telemetry to GRC workflows.
