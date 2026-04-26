# Compliance OS — Product Requirements Document

**Version**: 0.1 (Pre-MVP)
**Status**: Planning
**Last Updated**: 2026-04-26

---

## 1. Product Vision

### One-line description
AI-powered GRC platform that turns live CrowdStrike security telemetry into real-time compliance evidence, automated control testing, and threat-informed risk intelligence.

### Vision statement
Compliance OS eliminates the manual, screenshot-based evidence collection process that consumes thousands of hours per year in enterprises using security tools like CrowdStrike alongside GRC platforms like AuditBoard. Every IT control is tested continuously. Every risk score reflects today's threat landscape. Every audit is ready in real time — not at the end of a painful manual cycle.

### What we are not building
- A full enterprise GRC platform (not replacing ServiceNow GRC or Archer)
- A security operations tool (not competing with CrowdStrike's core)
- A generic compliance checklist tool (not Vanta or Drata)
- A detection engineering platform (not CardinalOps)

We are building the intelligent layer between security telemetry and compliance evidence — starting with the CrowdStrike ↔ AuditBoard gap.

---

## 2. Target Users

### Primary User: IT Auditor / IT Risk Manager

**Who they are**: Internal audit team member responsible for testing IT controls, collecting evidence, and reporting compliance posture to the CAE (Chief Audit Executive) and CISO.

**Current pain**: Spends 40–60% of audit time chasing evidence from the security team. Evidence is always stale. Can't answer "are controls working right now?" without a manual request cycle.

**What they need**: Controls pre-populated with current evidence. Status visible at any time. Findings tracked through to remediation automatically.

**Success metric**: Time to collect evidence for a full audit cycle drops from days to minutes.

---

### Secondary User: CISO / Security Manager

**Who they are**: Responsible for CrowdStrike deployment and security posture. Currently spends 15–30% of team's time responding to audit requests.

**Current pain**: Audit requests pull analysts from security work. Manual exports are repetitive and low-value. Has no visibility into how security data maps to compliance.

**What they need**: Audit requests handled automatically. Security team freed from evidence export work. Clear mapping between security findings and compliance obligations.

**Success metric**: Zero manual evidence export requests from audit team.

---

### Tertiary User: CAE / VP of Risk

**Who they are**: Owns the compliance program and board reporting. Responsible for risk register accuracy and executive reporting.

**Current pain**: Risk register updated quarterly by opinion. No real-time visibility into whether controls are working. Board reports take days to prepare.

**What they need**: Live compliance posture dashboard. Risk scores driven by real data. Board reports generated automatically.

**Success metric**: Board report prepared in under 1 hour using Compliance OS data.

---

## 3. Core Use Cases

### UC-1: Automated Evidence Collection
**Actor**: Auditor
**Trigger**: Audit cycle begins, control test opened
**Flow**:
1. Auditor opens control test in Compliance OS
2. System queries CrowdStrike API for relevant data
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
**Trigger**: Critical CrowdStrike detection or threshold change
**Flow**:
1. CrowdStrike event received (detection, new CVE, coverage drop)
2. AI determines risk register impact
3. Affected risks updated with new scores and evidence
4. Risk owners notified with context
5. Related controls flagged for immediate re-testing
6. Regulatory notification obligations assessed

**Success criteria**: Risk register reflects live threat environment within 5 minutes of CrowdStrike event

---

### UC-4: Finding Lifecycle Management
**Actor**: Auditor + Security Team
**Trigger**: Control test fails
**Flow**:
1. FAIL on control test auto-creates a finding
2. Finding assigned to security team owner
3. Ticket created in connected system (Jira / ServiceNow)
4. Remediation tracked in both systems
5. When CrowdStrike confirms fix → finding auto-closed
6. Audit trail preserved

**Success criteria**: Zero manual status updates between creation and closure

---

### UC-5: AuditBoard Sync (Optional)
**Actor**: System (automated)
**Trigger**: Evidence updated in Compliance OS
**Flow**:
1. Evidence collected and interpreted as normal
2. System checks if AuditBoard integration is enabled
3. If yes: pushes formatted evidence to matching AuditBoard control test
4. AuditBoard control test updated without manual action
5. Sync logged with status

**Success criteria**: AuditBoard reflects same evidence as Compliance OS within 10 minutes

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

## 4. Features

### MVP (Version 1.0) — Target: 8 weeks

#### F1: CrowdStrike Integration
- OAuth2 authentication with client ID / secret
- Agent coverage collection (all devices, status, version, policy)
- Vulnerability data collection (Falcon Spotlight — CVEs, severity, age)
- Detection data collection (last 24/48/72 hours, configurable)
- Automatic re-auth on token expiry
- Error handling and retry logic
- Sync status and health dashboard

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
- Control-to-data-source mapping (which CrowdStrike data tests which control)
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
- Auto-update trigger from CrowdStrike critical events

#### F6: Findings Management
- Auto-created from failed control tests
- Severity classification (Critical / High / Medium / Low)
- Owner assignment
- Due date tracking
- Status workflow (Open → In Remediation → Closed)
- Auto-close when CrowdStrike confirms remediation

#### F7: Integrations Hub
- CrowdStrike connector setup and testing
- AuditBoard connector setup and testing (optional)
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

| Layer | Technology |
|---|---|
| Frontend | Next.js 14 (App Router), React, TypeScript |
| Styling | Tailwind CSS, shadcn/ui |
| Backend | Next.js API Routes / Node.js |
| Database | PostgreSQL (production), SQLite (development) |
| ORM | Prisma |
| AI | Anthropic Claude API (claude-opus-4-7) |
| Auth | NextAuth.js |
| Job Scheduling | node-cron |
| Hosting | Vercel (frontend), Railway or Render (database) |

---

### Data Flow

```
CrowdStrike Falcon API
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
      └──► AuditBoard Connector (if enabled)
                │
                ▼
           AuditBoard API
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
- Card per connector (CrowdStrike, AuditBoard, etc.)
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
- CrowdStrike connector + agent coverage collection
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
- AuditBoard connector (optional sync)
- Integration management UI
- Dashboard with posture score
- Error handling, logging, reliability

### Phase 4 — Design Partner Launch (Week 15)
- Deploy to first design partner
- Collect feedback over 4-week audit cycle
- Iterate on AI evidence quality
- Refine UX based on real auditor workflow

---

## 11. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| AuditBoard API access requires partner agreement | High | Medium | Build standalone product first; AuditBoard connector is optional enhancement |
| CrowdStrike API rate limits at scale | Medium | Medium | Implement pagination, batching, caching; request rate limit increase for enterprise |
| AI evidence quality not trusted by auditors | Medium | High | Human approval step on all AI output; show raw data alongside summary; build feedback loop |
| CrowdStrike builds this natively | Low | High | Get to market with paying customers before they notice; acquire-ability is the exit, not competition |
| Long enterprise sales cycles delay revenue | High | Medium | Target mid-market ($500M–$2B revenue) first; design partner model bypasses procurement |
| Compliance frameworks change | Low | Low | Framework library is data, not code; update controls independently |

---

## 12. Open Questions

1. **AuditBoard API access**: Can we get sandbox/developer access without a full partner agreement? Needs outreach.
2. **CrowdStrike trial scope**: Does the 15-day trial include Spotlight (vulnerability) API? Needs testing.
3. **Evidence legal validity**: Do auditors require wet signatures or specific formats for certain frameworks? Needs validation with a Big 4 auditor.
4. **Data residency**: Do enterprise customers require evidence data to stay in specific regions? May require multi-region database.
5. **Framework licensing**: Do any compliance frameworks require licensing to distribute their control language? Needs legal review.

---

*Compliance OS — Product Requirements Document v0.1*
