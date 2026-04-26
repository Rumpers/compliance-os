# Compliance OS — Product Requirements Document

**Version**: 0.2 (Pre-MVP, refreshed for 2026 regulatory and market state)
**Status**: Planning
**Last Updated**: 2026-04-26

---

## 1. Product Vision

### One-line description
AI-powered GRC platform that turns live cybersecurity-platform telemetry into real-time compliance evidence, automated control testing, and threat-informed risk intelligence.

### Vision statement
Compliance OS eliminates the manual, screenshot-based evidence collection process that consumes thousands of hours per year in enterprises running a major cybersecurity platform alongside an enterprise GRC platform. Every IT control is tested continuously. Every risk score reflects today's threat landscape. Every audit is ready in real time — not at the end of a painful manual cycle.

### What we are not building
- A full enterprise GRC platform (not replacing ServiceNow GRC or Archer)
- A connected reporting / financial close platform (not competing with Workiva's core; their March 2026 AI-GRC launch validates the category but they went broad — financial + ESG + general GRC — with no native security-telemetry connectors)
- A security operations tool (not competing with the major EDR vendors' core SOC products)
- **A vendor-locked CSPM compliance dashboard** — e.g., CrowdStrike Falcon Cloud Security ships NIST / CIS / FedRAMP / PCI-DSS / HIPAA / GDPR compliance dashboards, but only against *Falcon's own* view of cloud workloads. We orchestrate evidence across any cybersecurity platform, identity provider, ticketing system, and cloud source — and produce audit-grade workpapers that survive PCAOB AS 1105 / 1215 review. Posture-only dashboards do not.
- A generic compliance checklist tool (not Vanta or Drata — agent-based posture checks; the existing Drata + Falcon Exposure Management integration that maps vulnerability data to one test (DCF-18) is the depth we are several layers deeper than)
- A detection engineering platform (not CardinalOps)
- An AI workpaper automation tool for *financial* audit (that is Kansaro, now Workiva)

We are building **the intelligent layer between security telemetry and audit evidence** — workflow-grade, multi-source, audit-defensible, cross-framework. Where Workiva went broad across the controller's office and EDR vendors went deep on their own posture data, we are going deep on the IT/security audit wedge no one currently owns end-to-end.

---

## 2. Target Users

### Primary User: IT Auditor / IT Risk Manager

**Who they are**: Internal audit team member responsible for testing IT controls, collecting evidence, and reporting compliance posture to the CAE (Chief Audit Executive) and CISO.

**Current pain**: Spends 40–60% of audit time chasing evidence from the security team. Evidence is always stale. Can't answer "are controls working right now?" without a manual request cycle.

**What they need**: Controls pre-populated with current evidence. Status visible at any time. Findings tracked through to remediation automatically.

**Success metric**: Time to collect evidence for a full audit cycle drops from days to minutes.

---

### Secondary User: CISO / Security Manager

**Who they are**: Owns the cybersecurity platform deployment (EDR, vulnerability management, detection) and overall security posture. In 2025, also personally accountable to the audit committee and increasingly the SEC. Has watched the SolarWinds CISO charges (Oct 2023, securities fraud claim survived motion to dismiss Jul 2024) and the Uber CISO conviction (May 2023) reshape what the role actually means.

**Current pain (2025–2026 reality)**:
- **Personal disclosure liability** — under SEC Cybersecurity Disclosure Rule (Item 1.05 8-K, effective Dec 18, 2023), the CISO has 4 business days from materiality determination to support an accurate public filing. Doing that without a single source of truth across security telemetry and control posture is a career-ending exposure.
- **Audit drag on the security team** — 15–30% of analyst hours go to evidence export, in a market where ISC2 reports ~4.8M unfilled cyber roles globally (2024 study). Every hour reformatting a CSV is an hour not on detection engineering.
- **Disconnected risk narrative** — when the CFO asks "what is our actual ransomware exposure," the CISO has cybersecurity-platform data, the CRO has a heatmap, and they don't reconcile.
- **Cyber insurance underwriting** — carriers now require evidence of controls operating, not policy attestations. (Premium hardening since 2022; coverage now contingent on demonstrable EDR coverage, MFA, backup hygiene.)
- **Vendor-dependency scrutiny** — post the July 19, 2024 major-EDR-vendor outage (single faulty content update grounded ~8.5M endpoints globally), boards and regulators are asking deeper questions about single-vendor security architectures and the controls around them.

**What they need**: A defensible, real-time view of security control state that doubles as audit evidence and SEC disclosure substrate. Audit cycle workload off the security team. AI assistance for materiality assessments under tight statutory clocks.

**Success metric**: Zero manual evidence export requests from audit team. Materiality determination supportable from a single data substrate within hours of a detection event.

---

### Tertiary User: CAE / VP of Risk

**Who they are**: Owns the compliance program and board reporting. Responsible for risk register accuracy and executive reporting.

**Current pain**: Risk register updated quarterly by opinion. No real-time visibility into whether controls are working. Board reports take days to prepare.

**What they need**: Live compliance posture dashboard. Risk scores driven by real data. Board reports generated automatically.

**Success metric**: Board report prepared in under 1 hour using Compliance OS data.

---

### Quaternary User: Board Director / Audit Committee Chair

**Who they are**: Independent director on the audit committee (or a dedicated risk/technology committee) of a public or large-private company. In 2025, increasingly carries personal duty-of-oversight exposure for cyber risk under the *Caremark* line of cases (extended by *Marchand v. Barnhill*, 2019, and *In re Boeing*, 2021 — board's affirmative duty to oversee mission-critical risks).

**Current pain (2025–2026 reality)**:
- **SEC Reg S-K Item 106 disclosure** — 10-K must describe board oversight of cyber risk and management's role in assessing/managing it. Vague language is no longer survivable.
- **NACD principles** — the *Director's Handbook on Cyber-Risk Oversight* (NACD/ISA, 2023 edition) establishes 5 board principles. Audit committees increasingly expected to demonstrate active oversight, not after-the-fact briefings.
- **Cadence problem** — board sees cyber once a quarter via a 30-slide deck. The deck is six weeks old by the time it is presented. When a *material* incident occurs, the board's institutional knowledge of the controls environment is already stale.
- **D&O exposure** — derivative suits citing inadequate cyber oversight are a growing vector. Directors now ask for documented oversight artifacts, not management assurances.
- **AI governance is the next agenda item** — many boards are now adding AI risk to the same committee that handles cyber. Standing oversight infrastructure has to be built once, used for both.

**What they need**:
- A read-only board view of compliance posture, top risks, and trend over time — accessible between meetings, not just the night before
- Auto-generated materiality narratives the board can rely on if a Form 8-K Item 1.05 trigger occurs
- A documented, queryable oversight trail — proof the board exercised duty-of-care, not just that management briefed it
- Peer benchmarking — am I better, worse, or normal vs. comparable companies

**Success metric**: Board can answer the SEC's three core questions (what is the risk, who oversees it, what is management doing) from primary-source data within one business day of any inquiry.

---

### Quinary User: External Auditor (Big 4 / Mid-Tier)

**Who they are**: Senior or manager-level IT auditor at Deloitte, PwC, KPMG, EY, BDO, Grant Thornton, or RSM. Executes the IT General Controls (ITGC) portion of SOX 404, SOC 2, ISO 27001, or PCI-DSS engagements. Signs the workpaper that goes into the engagement file.

**Current pain**: Issues a 200-line PBC ("Provided By Client") request list at engagement kickoff. Spends 30–40% of fieldwork hours chasing artifacts, reformatting CSVs, and reconciling versions. Cannot test full populations because client systems are opaque to them — falls back to sampling, which PCAOB inspections increasingly flag under AS 1105 when the underlying population is queryable. Repeats the entire cycle at rollforward (interim → year-end).

**What they need**:
- Read-only auditor seat into the client's Compliance OS tenant
- Evidence with full provenance chain (source, query, timestamp, hash)
- Population-level testing (not 25-of-1,891 samples)
- Re-performance capability — re-run any control test on demand, get current state
- Workpaper export with raw data attached for engagement file retention (7 years under PCAOB AS 1215)
- Independence preserved — auditor consumes evidence but never operates client systems

**Success metric**: Reduce IT audit fieldwork hours by 40% on engagements where the client uses Compliance OS. Sustain or improve PCAOB inspection outcomes.

---

## 3. Core Use Cases

### UC-1: Automated Evidence Collection
**Actor**: Auditor
**Trigger**: Audit cycle begins, control test opened
**Flow**:
1. Auditor opens control test in Compliance OS
2. System queries cybersecurity platform API for relevant data
3. AI interprets raw data in compliance context
4. Formatted evidence package attached to control test
5. Control status set automatically (PASS / FAIL / EXCEPTION)
6. Auditor reviews and approves or overrides

**Success criteria**: End-to-end in under 3 minutes with no manual steps

---

### UC-2: Continuous Control Monitoring
**Actor**: System (automated)
**Trigger**: Scheduled job (daily default, configurable)
**Flow**:
1. System pulls fresh data from all connected sources
2. AI re-evaluates each control against current data
3. Status changes trigger notifications to control owners
4. Evidence updated with timestamp
5. Control health history maintained

**Success criteria**: No control test is more than 24 hours stale

---

### UC-3: Live Risk Register Update
**Actor**: System (event-driven)
**Trigger**: Critical cybersecurity-platform detection or threshold change
**Flow**:
1. Security-platform event received (detection, new CVE, coverage drop)
2. AI determines risk register impact
3. Affected risks updated with new scores and evidence
4. Risk owners notified with context
5. Related controls flagged for immediate re-testing
6. Regulatory notification obligations assessed

**Success criteria**: Risk register reflects live threat environment within 5 minutes of security-platform event

---

### UC-4: Finding Lifecycle Management
**Actor**: Auditor + Security Team
**Trigger**: Control test fails
**Flow**:
1. FAIL on control test auto-creates a finding
2. Finding assigned to security team owner
3. Ticket created in connected system (Jira / ServiceNow)
4. Remediation tracked in both systems
5. When the cybersecurity platform confirms fix → finding auto-closed
6. Audit trail preserved

**Success criteria**: Zero manual status updates between creation and closure

---

### UC-5: GRC Platform Sync (Optional)
**Actor**: System (automated)
**Trigger**: Evidence updated in Compliance OS
**Flow**:
1. Evidence collected and interpreted as normal
2. System checks if GRC-platform integration is enabled
3. If yes: pushes formatted evidence to matching control test in customer's GRC tenant
4. GRC-platform control test updated without manual action
5. Sync logged with status

**Success criteria**: Customer's GRC platform reflects same evidence as Compliance OS within 10 minutes

---

### UC-6: Board Report Generation
**Actor**: CISO / CAE
**Trigger**: Manual request
**Flow**:
1. User requests board report for time period
2. AI reads compliance posture data, risk register, finding history
3. Generates executive summary with key metrics
4. Creates visual risk heatmap
5. Highlights trend vs. prior period
6. Exports to PDF or PowerPoint format

**Success criteria**: Board-ready report generated in under 60 seconds

---

### UC-7: PBC List Automation (External Auditor)
**Actor**: External auditor (Big 4 / mid-tier)
**Trigger**: Engagement kickoff — auditor uploads or composes the PBC request list
**Flow**:
1. External auditor logs into client's Compliance OS via read-only auditor seat
2. Auditor uploads PBC list (CSV / Excel) or selects from pre-mapped framework templates
3. System matches each PBC item to existing control tests and evidence
4. For matched items: evidence package auto-bundled with provenance chain
5. For unmatched items: gap report generated, routed to client control owners
6. Auditor reviews each evidence bundle; can request re-performance against live data
7. Approved evidence bundles exported to workpaper format (PDF + raw data attachment)

**Success criteria**: 70%+ of standard ITGC PBC items fulfilled without manual client effort. Time from PBC issuance to evidence completion drops from 4–6 weeks to under 5 business days.

---

### UC-8: Population-Based Control Testing
**Actor**: External auditor or internal IT auditor
**Trigger**: Auditor opens a control test that historically required sampling
**Flow**:
1. Auditor selects control (e.g., "All endpoints have approved EDR agent installed")
2. System queries the cybersecurity platform for the full population at the test date
3. AI evaluates every record against the control criterion — no sampling
4. Output: total population N, exceptions M, exception list with root cause per record
5. Auditor reviews exceptions only (not the entire population)
6. Workpaper records: population tested, methodology, exceptions, disposition

**Success criteria**: 100% population testing for all controls where data source is queryable. Exception rate calculated from full population, not extrapolated from sample. Defensible under PCAOB AS 1105 and ISA 500 evidence sufficiency standards.

---

### UC-9: Walkthrough Documentation
**Actor**: External auditor (during interim fieldwork)
**Trigger**: Auditor scheduled to perform control walkthrough with client owner
**Flow**:
1. Auditor opens control in Compliance OS auditor view
2. System displays: control description, framework mapping, data sources wired, last 90 days of test history, any exceptions
3. Auditor conducts walkthrough conversation with client control owner
4. Auditor annotates walkthrough notes directly on control record
5. System generates walkthrough memo template populated with system-of-record facts
6. Memo exported to engagement file with full data lineage attached

**Success criteria**: Walkthrough documentation reduced from 2–3 hours per control to under 30 minutes. Design effectiveness assessment supported by 90 days of operating evidence rather than a single point-in-time observation.

---

## 3.5 Audit Standards Alignment

Compliance OS is designed so that artifacts produced by the platform meet the evidentiary requirements of the standards external auditors are bound by. This is what allows the GRC-platform-replacement (or bridge) motion and the Big 4 channel motion to be more than marketing.

| Standard | Body | Requirement | How Compliance OS supports |
|---|---|---|---|
| **AS 1105** | PCAOB | Audit evidence must be sufficient and appropriate | Population-level data with provenance chain, not screenshots |
| **AS 1215** | PCAOB | Audit documentation retained 7 years, prepared with sufficient detail to enable an experienced auditor to understand the work | Immutable evidence store, hash-pinned raw payloads, AI prompt + model versioning |
| **AS 2201** | PCAOB | Audit of ICFR — ITGC effectiveness must be tested over the period | 365-day test history per control, no point-in-time gaps |
| **AT-C 105 / 205 / 320** | AICPA | Attestation engagements (SOC 1 / SOC 2) — examination evidence and reporting | Trust Service Criteria pre-mapped; evidence formatted for SOC report inclusion |
| **ISA 500** | IAASB | Audit evidence — relevance and reliability | Source-system queries with method documented for re-performance |
| **ISAE 3402** | IAASB | International equivalent of SOC 1 — service organization controls | Cross-walk from SOC 2 control library to ISAE 3402 control objectives |
| **NIST CSF 2.0** | NIST | Govern / Identify / Protect / Detect / Respond / Recover (Feb 2024 release added GOVERN) | All six functions modelled in framework library; GOVERN-function controls prioritized |
| **DORA RTS** | ESAs (EU) | Continuous ICT risk management for financial entities (effective Jan 17, 2025) | Continuous control monitoring satisfies "ongoing" requirement; incident classification supports 24/72-hour reporting deadlines |

**Independence preserved**: Compliance OS is consumed by the auditor, not operated by them. The auditor reviews evidence, exercises professional skepticism, and signs the workpaper. AI-generated summaries are explicitly labelled as such; raw data and provenance remain authoritative. This is consistent with **AICPA ET 1.295** independence rules and **PCAOB Rule 3520** on auditor independence — the platform is a client tool that the auditor inspects, not a non-audit service the auditor provides.

---

## 4. Features

### MVP (Version 1.0) — Target: 8 weeks

#### F1: Cybersecurity Platform Integration
- OAuth2 authentication with client ID / secret
- Agent coverage collection (all devices, status, version, policy)
- Vulnerability data collection (CVEs, severity, age)
- Detection data collection (last 24/48/72 hours, configurable)
- Automatic re-auth on token expiry
- Error handling and retry logic
- Sync status and health dashboard
- MVP supports one major EDR vendor; multi-vendor support roadmap (V2.0)

#### F2: AI Evidence Interpretation
- Agent coverage → compliance evidence summary
- Vulnerability data → patch compliance narrative
- Detection data → incident summary for audit
- Per-framework output (SOC2, NIST, PCI-DSS, HIPAA)
- Plain-English summary suitable for direct auditor use
- Control status determination (PASS / FAIL / EXCEPTION)
- Exception identification and root cause description
- Confidence scoring

#### F3: Controls Management
- Pre-seeded control library for 5 frameworks (SOC2, NIST CSF, PCI-DSS, HIPAA, ISO27001)
- Control-to-data-source mapping (which security-platform data tests which control)
- Control test history
- Manual evidence upload (for controls not covered by automation)
- Control status dashboard
- Filter by framework, status, category

#### F4: Evidence Library
- All collected evidence stored with timestamp and source
- Raw data attached as downloadable artifact
- AI summary displayed
- Auditor approval / override workflow
- Evidence search and filter

#### F5: Risk Register
- Basic risk entry (title, description, likelihood, impact, owner)
- Risk score calculation (likelihood × impact, 1–25 scale)
- Control mapping (which controls mitigate which risks)
- Risk status (Open / Mitigated / Accepted / Closed)
- Auto-update trigger from critical security-platform events

#### F6: Findings Management
- Auto-created from failed control tests
- Severity classification (Critical / High / Medium / Low)
- Owner assignment
- Due date tracking
- Status workflow (Open → In Remediation → Closed)
- Auto-close when the cybersecurity platform confirms remediation

#### F7: Integrations Hub
- Cybersecurity-platform connector setup and testing
- GRC-platform connector setup and testing (optional, bridge mode)
- Connection health indicators
- Sync history and logs
- Manual sync trigger

#### F8: Dashboard
- Overall compliance posture score (% controls passing)
- Score by framework
- Open findings count by severity
- Risk register summary
- Last sync timestamp
- Recent activity feed

---

### Version 1.5 — Target: Month 4–6

#### F9: Scheduled Sync Engine
- Configurable sync schedule (hourly / daily / weekly per data type)
- Email / Slack notifications on status changes
- Sync failure alerts
- Retry with exponential backoff

#### F10: Framework Coverage Heatmap
- MITRE ATT&CK coverage visualization
- Gap identification (techniques with no coverage)
- Progress tracking over time

#### F11: Dollar Risk Quantification
- FAIR-based risk scoring model
- Asset criticality weighting
- Industry benchmark comparison
- Dollar exposure range (min / likely / max)
- ROI calculation for remediation

#### F12: Multi-Framework Control Mapping
- Single control test satisfies multiple frameworks simultaneously
- Cross-walk view (SOC2 → NIST → ISO mapping)
- Framework overlap report for audit efficiency

---

### Version 2.0 — Target: Month 9–12

#### F13: Additional Connectors
- Okta (identity and access data)
- AWS CloudTrail (cloud activity)
- Jira (bi-directional finding sync)
- ServiceNow (ITSM integration)
- Splunk / Elastic (alternative security data sources)

#### F14: Regulatory Breach Notification Engine
- Automatic assessment of notification obligations on breach detection
- HIPAA 72-hour, GDPR 72-hour, SEC 4-day detection
- Draft notification generated by AI
- Deadline countdown with escalation

#### F15: Board Report Generator
- One-click board-ready PDF/PowerPoint export
- Executive summary (AI-generated, plain English)
- Risk trend charts
- Peer benchmarking data
- Customizable branding

#### F16: Tenant Management (for MSSPs)
- Multi-tenant architecture
- Per-client compliance posture
- Aggregated reporting across clients
- White-label option

---

## 5. Technical Architecture

### Stack

| Layer | Technology | Version notes (as of 2026) |
|---|---|---|
| Frontend | Next.js (App Router), React, TypeScript | Next.js 15 (stable since Oct 2024); React 19 (stable since Dec 2024) |
| Styling | Tailwind CSS, shadcn/ui | Tailwind v4 |
| Backend | Next.js API Routes / Node.js | Node 20 LTS or 22 LTS |
| Database | PostgreSQL (production), SQLite (development) | Postgres 16 |
| ORM | Prisma | Prisma 5.x |
| AI | Anthropic Claude API | `claude-opus-4-7` for evidence interpretation; `claude-haiku-4-5-20251001` for low-latency UI summarization. Prompt caching enabled to control inference cost. |
| Auth | Auth.js (formerly NextAuth.js) | v5 |
| Job Scheduling | node-cron (MVP) → BullMQ + Redis (V1.5) | — |
| Hosting | Vercel (frontend), Neon or Supabase (Postgres), Upstash (Redis) | — |
| Observability | OpenTelemetry → Vercel Observability or Datadog | — |

---

### Data Flow

```
Cybersecurity Platform API (EDR / VM / detection)
      │
      ▼
Connector Layer
(auth, rate limiting, retry, pagination)
      │
      ▼
Collector Layer
(agentCoverage, vulnerabilities, detections)
      │
      ▼
Normalizer
(vendor-agnostic SecurityEvent format)
      │
      ▼
AI Interpretation Layer (Claude)
(maps data to control language, generates narrative)
      │
      ▼
Control Mapping Engine
(routes evidence to correct controls by framework)
      │
      ├──► Database (evidence, control tests, findings, risks)
      │
      └──► GRC Platform Connector (if enabled, bridge mode)
                │
                ▼
           Customer's GRC platform API
```

---

### Connector Interface

All data source connectors implement `ComplianceConnector`:
```typescript
interface ComplianceConnector {
  name: string
  test(): Promise<boolean>
  collect(): Promise<SecurityEvent[]>
}
```

All GRC destination connectors implement `GRCConnector`:
```typescript
interface GRCConnector {
  name: string
  test(): Promise<boolean>
  pushEvidence(controlId: string, evidence: EvidencePayload): Promise<void>
  pullControls?(): Promise<ExternalControl[]>
}
```

New connectors can be added without modifying core logic.

---

### Database Schema (Core Tables)

```
Framework      — SOC2, NIST, PCI-DSS, HIPAA, ISO27001
Control        — Individual control requirements per framework
ControlTest    — Test instance for a control (has status + evidence)
Evidence       — Evidence items attached to control tests
Risk           — Risk register entries
RiskControl    — Many-to-many: risks ↔ controls
Finding        — Audit findings from failed control tests
Integration    — Connector configurations (encrypted)
SyncLog        — History of sync jobs
```

---

### AI Prompt Architecture

Evidence interpretation prompts follow a structured template:

```
System: You are a compliance expert interpreting security telemetry
        for audit evidence. Be precise. Auditors attach this directly
        to control tests. Never speculate. Only report what the data shows.

User:   Framework: {framework}
        Control: {controlId} — {controlTitle}
        Data type: {dataType}
        Raw data: {json}

        Produce:
        1. Status: PASS | FAIL | EXCEPTION
        2. Coverage/compliance percentage
        3. Exception list (if any)
        4. Auditor summary (2-3 sentences, plain English)
        5. Framework control references satisfied
        6. If FAIL: finding title, description, severity
```

Prompts are versioned. Output is validated against a Zod schema before storage.

---

## 6. API Specification

### Internal API Routes

#### Sync

```
POST /api/sync/crowdstrike
  Body: { integrationId: string, dataTypes?: string[] }
  Response: { jobId: string, status: "started" }

GET /api/sync/status/:jobId
  Response: { status: "running"|"complete"|"error", summary: string }
```

#### Controls

```
GET /api/controls
  Query: ?framework=SOC2&status=FAIL&category=Endpoint
  Response: Control[]

GET /api/controls/:id
  Response: Control & { tests: ControlTest[], latestEvidence: Evidence[] }

POST /api/controls/:id/test
  Body: { manual?: boolean }
  Response: ControlTest
```

#### Evidence

```
GET /api/evidence
  Query: ?controlId=&source=crowdstrike&from=&to=
  Response: Evidence[]

POST /api/evidence
  Body: { controlTestId, title, summary, rawData, source }
  Response: Evidence

POST /api/evidence/:id/approve
  Response: Evidence (status updated)
```

#### Risks

```
GET /api/risks
  Query: ?status=OPEN&minScore=15
  Response: Risk[]

POST /api/risks
  Body: { title, description, likelihood, impact, owner }
  Response: Risk

PATCH /api/risks/:id
  Body: Partial<Risk>
  Response: Risk
```

#### Integrations

```
GET /api/integrations
  Response: Integration[] (config fields redacted)

POST /api/integrations
  Body: { type: "crowdstrike"|"auditboard", config: object }
  Response: Integration

POST /api/integrations/:id/test
  Response: { connected: boolean, error?: string }

DELETE /api/integrations/:id
  Response: 204
```

---

## 7. UI/UX Requirements

### Navigation
- Sidebar navigation: Dashboard, Controls, Evidence, Risks, Findings, Integrations
- Top bar: Last sync time, sync now button, notifications
- Responsive but desktop-first (audit work is desktop)

### Dashboard
- Compliance posture score (large, prominent — single number 0–100)
- Framework breakdown (SOC2: 94%, NIST: 87%, etc.)
- Open findings by severity (Critical: 2, High: 5, Medium: 12)
- Recent sync activity
- Quick-action buttons: Run Sync, View Findings, Add Risk

### Controls List
- Filter by: Framework, Status (PASS/FAIL/PENDING), Category, Data Source
- Sort by: Last Tested, Status, Control ID
- Inline status indicator (green/red/yellow dot)
- Last tested timestamp
- Click through to control detail

### Control Detail
- Control title and description
- Framework mapping (all frameworks this control satisfies)
- Latest evidence (AI summary, status, timestamp)
- Evidence history (previous test results)
- Any open findings
- Manual evidence upload option
- Run test now button

### Evidence Detail
- AI-generated summary (prominent)
- Status badge (PASS/FAIL/EXCEPTION)
- Data source and collection timestamp
- Raw data (collapsible JSON viewer)
- Auditor approval controls
- Download as PDF option

### Risk Register
- Risk heatmap (5×5 likelihood/impact grid, risks plotted as dots)
- Table view with sort/filter
- Risk detail modal with full description, controls, history
- Inline editing of likelihood/impact scores
- Auto-updated badge on risks recently changed by sync

### Findings
- Prioritized list (Critical first)
- Status workflow (kanban or table view, configurable)
- Due date countdown
- Owner assignment
- Link to source control test and evidence

### Integrations
- Card per connector (cybersecurity platforms, GRC platforms, etc.)
- Connection status (green connected / red disconnected / grey not configured)
- Setup flow in modal (credentials → test → save)
- Sync history table (last 10 syncs, status, duration, summary)
- Manual sync trigger button

---

## 8. Non-Functional Requirements

### Performance
- Dashboard loads in under 2 seconds
- Evidence collection sync completes in under 5 minutes for 5,000 endpoints
- AI interpretation per control under 15 seconds
- API responses under 500ms (excluding AI calls)

### Security
- All integration credentials encrypted at rest (AES-256)
- API keys never exposed in client-side code
- All API routes authenticated
- Audit log for all user actions
- SOC2 Type II compliant infrastructure (target year 2)

### Reliability
- Sync failures do not affect existing evidence
- Retry logic with exponential backoff on connector failures
- Stale evidence clearly marked (last tested > 7 days)
- Graceful degradation if AI API unavailable (raw data stored, interpretation queued)

### Multi-tenancy (V2)
- Complete data isolation between tenants
- Tenant-level integration configuration
- Per-tenant compliance posture scoring

---

## 9. Success Metrics

### Product Metrics
| Metric | Month 3 Target | Month 12 Target |
|---|---|---|
| Evidence collection time | < 3 min | < 1 min |
| Manual evidence requests eliminated | 80% | 95% |
| Control test freshness | < 24 hours | < 6 hours |
| Risk register update latency | < 10 min | < 2 min |

### Business Metrics
| Metric | Month 6 Target | Month 18 Target |
|---|---|---|
| Paying customers | 3 | 20 |
| MRR | $10K | $100K |
| NPS | > 40 | > 60 |
| Churn | < 5% | < 3% |

---

## 10. MVP Launch Plan

### Phase 0 — Validation (Weeks 1–2)
- Interview 10 IT auditors and IT risk managers
- Confirm manual evidence collection pain
- Confirm willingness to pay
- Identify 3 design partner candidates

### Phase 1 — Foundation (Weeks 3–6)
- Project setup (Next.js, Prisma, Tailwind)
- Cybersecurity-platform connector + agent coverage collection
- AI interpretation layer (Claude)
- Basic database schema
- Control library seeded (SOC2 + NIST)

### Phase 2 — Core Product (Weeks 7–10)
- Evidence library UI
- Controls dashboard
- Sync engine (manual + scheduled)
- Basic risk register
- Findings management

### Phase 3 — Connectors + Polish (Weeks 11–14)
- GRC-platform connector built (bridge mode is the primary deployment posture, not optional)
- Integration management UI
- Dashboard with posture score
- Error handling, logging, reliability

### Phase 4 — Design Partner Launch (Week 15)
- Deploy to first design partner
- Collect feedback over 4-week audit cycle
- Iterate on AI evidence quality
- Refine UX based on real auditor workflow

### Phase 5 — GRC Platform Partner Engagement (Weeks 16–24)
**Strategic milestone — separate from product execution.**

The category-leading enterprise GRC platform was acquired by a PE firm (May 2024, ~$3B) and PE typical hold of 5–7 years places its exit window at ~2028–2031. To be on the M&A consideration list before that exit, Compliance OS must be a *visible, customer-validated, integrated* presence in that ecosystem by ~2027. (Specific named buyer kept in pitch deck Acquisition Thesis.)

Concrete actions:
- **Apply to the partner program** as soon as we have one paying bridge-mode customer to reference
- **Pursue marketplace listing** — primary distribution path to ~2,000+ enterprise customers
- **Engage product / BD / corp dev** with a customer success story and the bridge-mode integration as the hook
- **Brief Big 4 advisory practices** that already implement the platform — they are the influence path into product roadmap conversations
- **Track PE-portfolio activity** — note any compliance-adjacent acquisitions or partnership announcements that signal direction; respond fast if the PE owner shows interest in a competing player
- **Maintain standalone product as defection path** — if price hikes hit customer renewals (typical PE pattern), be ready with rip-and-replace migration tooling

**Deliverable**: 3+ joint customers documented as references; partner program tier achieved; named contact at the GRC platform's product / corp dev team.

---

## 11. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Leading GRC-platform API access requires partner agreement (now PE-owned, gating may tighten) | High | Medium | Build standalone product first; bridge connector is enhancement; pursue both bridge and replacement motions in parallel |
| Cybersecurity-platform API rate limits at scale | Medium | Medium | Pagination, batching, server-side caching; request enterprise rate-limit increase; for very large tenants use the platform's bulk-export / data-replication channel rather than API polling |
| AI evidence quality not trusted by auditors | Medium | High | Human approval step on all AI output; raw data shown alongside summary; prompt and model versioning recorded with each artifact; feedback loop trains prompt revisions |
| **Vendor concentration concerns post the Jul 19, 2024 major-EDR outage** | Medium | Medium | Roadmap to multi-EDR support (additional major vendors) by V2.0; position as vendor-agnostic compliance layer, not a single-vendor skin |
| **Major EDR vendor extends natively into full GRC** — yellow-flag evidence: CrowdStrike Spring 2026 platform release explicitly markets "expanded governance"; AIDR (GA Dec 2025) extended Falcon to AI-attack surface with governance framing; Falcon Cloud Security CSPM already ships compliance dashboards (NIST / CIS / PCI / HIPAA / GDPR) for cloud posture; Drata + Falcon Exposure Management integration already maps vulnerability data to one specific compliance test (DCF-18) | Medium → Medium-High | Move fast to be acquisition-ready before this matures; differentiate explicitly on workflow-grade (PBC / walkthroughs / control-test lifecycle), multi-source (not vendor-locked to one EDR), audit-defensible provenance chain (PCAOB AS 1105 / 1215), and cross-framework mapping; build framework-mapping data moat; deepen Big 4 channel relationships that increase strategic value to acquirer |
| **AI in audit gets restricted by PCAOB / IAASB guidance** | Medium | High | Position AI as decision-support, not decision-maker; auditor reviews and approves every artifact; align with emerging IAASB technology guidance and AICPA SAS 145 risk-assessment standard |
| Long enterprise sales cycles delay revenue | High | Medium | Target upper mid-market ($500M–$2B revenue) and PE-backed companies first; design partner model bypasses procurement |
| **EU AI Act classification** (compliance-related AI may be deemed higher-risk) | Low | Medium | Document model lineage, inputs, outputs, and human-in-the-loop controls now; design for Annex III obligations even if classification narrower |
| Compliance frameworks change | Low | Low | Framework library is data, not code; update controls independently. NIST CSF 2.0 already absorbed; CMMC 2.0 Final Rule (Oct 2024) on roadmap |
| **Cyber insurance carriers become an alternative buyer of the same data** | Low | Low | Opportunity, not threat — partner with carriers as evidence consumer; potential underwriting-data product |
| **PE owner of the leading GRC platform acquires a competing compliance-automation player first** (Hyperproof, Onspring, lower-tier of Vanta/Drata) and bolts it in | Medium | High | Move quickly to be the visible incumbent integration; engage GRC-platform partner / corp dev teams early in 2026 so the PE owner knows we exist; build features that would be redundant in any competing acquisition (deep, multi-source security-telemetry evidence pipeline) |
| **Leading GRC platform ships a native cybersecurity-platform connector internally before we reach material ARR** | Medium | High | Speed to first 50 customers; depth advantage (full evidence chain, AI-interpreted rationale, audit-grade provenance) over thin posture signals; framework-mapping moat that is hard to replicate quickly; Big 4 channel relationships that increase switching cost |
| **Customer-defection wedge from post-PE-acquisition price hikes at the leading GRC platform** is wasted because we are not ready to receive defectors | Medium | Medium | Standalone deployment must be production-grade by month 9, not just a fallback narrative; have a rip-and-replace migration path with imported control library, evidence history, and risk register |
| **Workiva announces a security-telemetry connector** — they launched their AI-Powered GRC Platform Mar 9, 2026 and acquired Kansaro for AI auditor workflow; security telemetry is the obvious next gap | Medium | High | Build the deepest single-platform evidence pipeline on the market (full provenance, AI rationale, framework mapping, re-performance hook), then add multi-vendor; make it harder to replicate than to acquire; engage Workiva BD/corp dev as a parallel acquisition path |
| **Workiva acquires a competing security-telemetry-to-GRC startup before us** (the Kansaro pattern repeated for the IT-audit vertical) | Medium | High | Be visible — get to first paying customers fast, publish technical content on the security-telemetry-to-audit-evidence wedge, attend IIA / ISACA / RSA where the Workiva product team is recruiting acquisition targets |
| **Workiva and the leading enterprise GRC platform converge on the same AI-GRC feature set**, commoditizing the AI evidence layer | Low | Medium | Defensibility is the security-telemetry depth and framework-mapping data moat — AI features alone are commoditizing across the category |

---

## 12. Open Questions

1. **Leading GRC-platform API access (post-PE-acquisition)**: PE thesis (May 2024) is bolt-on M&A and ARR growth — does that make API gating tighter (protect rev) or looser (drive ecosystem)? Needs partner-team outreach to product / BD.
2. **Cybersecurity-platform trial scope**: Does the major-EDR vendor's free / developer trial include vulnerability-management and bulk-export channels? Needs testing. Vendor developer-program access is a possible alternative path.
3. **Evidence legal validity & AI disclosure**: Under PCAOB AS 1215 and AICPA AT-C 105/205, must AI-generated summaries be explicitly disclosed in workpapers? IAASB issued exposure draft on technology-assisted audits (2023–2024) — needs alignment with finalized guidance. Validate with Big 4 quality-and-risk-management partner.
4. **Data residency**: DORA + GDPR + UK GDPR + state-level US (NY DFS, CCPA) all have implications. EU customers will likely require data-in-EU; need multi-region Postgres (Neon supports this) and careful sub-processor mapping.
5. **Framework licensing**: ISO 27001 control text is copyrighted by ISO/IEC; AICPA TSC text by AICPA. Pre-mapped controls may need to paraphrase or license. Needs legal review before public listing of full control library.
6. **EU AI Act classification of compliance AI**: Risk tier depends on use — likely "limited risk" with transparency obligations rather than "high risk." Document model cards, inputs, outputs, and human-in-the-loop now to be ready for either classification.
7. **SOC 2 Type II for ourselves**: Realistically need our own SOC 2 to sell to enterprises. Earliest practical: 12 months after first paying customer (need 6 months of operating evidence, then 6 months of audit window).
8. **Multi-EDR support timeline**: Post-Falcon-outage, will design partners require multi-EDR commitment in the contract? May force MS Defender or SentinelOne support earlier than V2.0.
9. **Cyber insurance distribution**: Should evidence packages be exportable to underwriter format (Marsh, Aon, WTW questionnaires)? Could become a meaningful ARR uplift channel.

---

*Compliance OS — Product Requirements Document v0.2*
