# Compliance OS — Pitch Deck

> AI-powered compliance intelligence that closes the gap between security telemetry and audit evidence

---

## Slide 1 — The Setup

**Every large enterprise has two groups who both care about security.**

The **Security Team** lives in CrowdStrike. They see every threat, every vulnerability, every misconfigured endpoint in real time. They have the most accurate picture of the organization's security posture that has ever existed.

The **Audit & Compliance Team** lives in AuditBoard. They manage controls, run audits, maintain the risk register, and answer the question every board member asks: *"Are our controls actually working?"*

**These two teams share the same building. Their systems share nothing.**

---

## Slide 2 — The Validation Signal

**The market just paid hard cash for the AI-for-auditors thesis. Twice. From a $WK public-company balance sheet.**

| Move | When | What it signals |
|---|---|---|
| **Workiva acquired Kansaro** (AI-powered workpaper automation, founders Laird / Joubert / Newcomer) | 2025–2026 | AI-for-auditors is now an acquirable category. Workiva will not have spent the capital otherwise. |
| **Workiva launched the AI-Powered Workiva GRC Platform** at the IIA Great Audit Minds conference | **March 9, 2026** | A public company is now formally committed to AI-driven evidence analysis, real-time control-health dashboards, and AI-mapped risks/controls as the new center of GRC. |
| **AuditBoard acquired by Hg Capital** at reported ~$3B valuation | May 2024 | The category leader is now PE-backed with a 5–7 year exit clock. Bolt-on M&A is the playbook. |

**Crucially — Workiva went broad. We go deep on the wedge they did not pursue.**

Workiva has 70+ connectors. They are all financial-system-oriented: Oracle, Salesforce, Workday, BlackLine, Persefoni. They have **no native CrowdStrike or security-telemetry connector**. The deep, audit-grade pipeline from security telemetry to compliance evidence is unowned by every AI-GRC entrant in the market.

**That is the wedge Compliance OS owns.** Same M&A logic Workiva applied to financial audit (Kansaro), applied to the IT/security audit vertical no one else has built for.

---

## Slide 3 — The Problem

### What happens every audit cycle

```
Auditor opens AuditBoard
  → Creates control test: "Verify endpoint protection on all devices"
  → Sends manual request to IT Security team
  → Waits 3-5 days

IT Security analyst
  → Logs into CrowdStrike
  → Exports CSV report
  → Formats it manually
  → Emails it back

Auditor uploads file as evidence
  → Already stale
  → Process repeats for 200 more controls
```

**A typical Fortune 500 runs 6+ audits per year. Each has 50–300 IT controls. Each control needs evidence. Security-related controls are 40–60% of the total.**

This means **thousands of manual evidence requests per year** — each pulling a senior security analyst away from security work.

### The deeper problem

AuditBoard's risk register shows risks rated by human opinion: *"Ransomware Risk: High."*

Meanwhile CrowdStrike knows:
- 3 peers in your industry were hit by ransomware this month
- You have 47 unpatched endpoints with the exact CVE being exploited
- One belongs to your CFO
- Last week CrowdStrike blocked an intrusion matching the same threat actor

**None of that intelligence reaches the risk manager. The board is making decisions based on last year's thinking.**

---

## Slide 4 — Three Lenses on the Same Pain

The same gap surfaces across three roles, each with a *current, personal* reason to act in 2026.

| | **Senior Big 4 IT Auditor** | **Fortune 500 CISO** | **Independent Board Director** |
|---|---|---|---|
| **The 2026 pressure** | PCAOB AS 1105 — sampling 25-of-1,891 endpoints is no longer defensible when the population is queryable. AICPA candidate volume at 20-year low. Annual fee compression of 10–15%. | SEC Item 1.05 8-K (4-business-day materiality clock). Personal exposure post-SolarWinds CISO action (Oct 2023, securities-fraud claim survived Jul 2024 motion to dismiss) and Uber CISO conviction (May 2023). | SEC Reg S-K Item 106 (board oversight disclosure). *Caremark / Marchand / Boeing* duty-of-oversight applies to cyber. D&O exposure from derivative suits is rising. |
| **The structural problem** | PBC list of 200+ items per engagement. 30–40% of fieldwork hours on evidence chase. Workpaper retention 7 years under PCAOB AS 1215. | 15–30% of analyst time on audit support — in a market with ~4.8M unfilled cyber roles (ISC2, 2024). Four parallel narratives (audit, board, insurance, regulator) that don't reconcile. | Quarterly 30-slide deck is 4–6 weeks stale by the time the board sees it. No view between meetings. NACD Director's Handbook 5th ed (2023): oversight must be continuous. |
| **What they need** | Population testing with provenance chain. Re-performance on demand. Workpaper-ready exports. Independence preserved (consume evidence, never operate client systems). | Single substrate that serves audit + board + insurance + regulator. Materiality assessment support. Audit drag off the security team. | Read-only board portal. Documented oversight trail (discoverable on *their* side). Materiality narrative on demand. Peer benchmarking. |
| **What sells them** | "40% of IT-audit fieldwork hours back, defensible under AS 1105 and AS 1215, with the methodology embedded." | "The same data that proves controls work for the audit committee proves them for the SEC, the cyber insurance carrier, and the regulator — and frees my team to do security work." | "Convert *we trust management* into *we have independently observable evidence*. That is the difference between a Caremark defense that holds and one that does not." |

> Detailed first-person memos from each persona — including the full set of regulatory references and the structural arguments — are in the **Appendix** at the end of this deck.

---

## Slide 5 — Why Now

Four forces converging in 2025–2026:

**1. Regulatory pressure at a structural inflection**
SEC Cyber Disclosure (live since Dec 2023), DORA (live since Jan 17, 2025), NIS2 (transposition deadline Oct 17, 2024), CMMC 2.0 (Final Rule Oct 15, 2024), NIST CSF 2.0 (Feb 2024), PCI-DSS v4.0.1 (full enforcement Mar 31, 2025), EU AI Act (in force Aug 2024) — all require **continuous demonstrable controls**, not annual audits. The manual screenshot-and-CSV process is mathematically incompatible with the new compliance posture cadence.

**2. The 2024–2025 incident wave permanently raised the bar**
- **Change Healthcare ransomware (Feb 2024)** — UnitedHealth-owned, BlackCat ransomware, ~$2.9B+ direct cost reported, disrupted ~one-third of US healthcare claims processing. Triggered HHS HIPAA enforcement focus.
- **Snowflake credential incidents (May–Jul 2024)** — ~165 customer environments compromised via stolen credentials per Mandiant; Ticketmaster, AT&T, Santander, LendingTree among confirmed victims. Reframed third-party risk for every board.
- **CrowdStrike Falcon outage (Jul 19, 2024)** — single faulty content update grounded ~8.5M Windows endpoints globally. Delta lawsuit and others created the precedent question: who is liable for security-vendor reliability, and how is it evidenced.
- **MOVEit (CL0P, 2023, still litigating in 2025)** — 2,700+ orgs, 95M+ records — set the template for vulnerability-to-extortion at scale.

Each event made *evidence of working controls* a board-level demand, not a back-office artifact.

**3. AI makes the translation layer possible — and (per Slide 2) the market just confirmed it.**
Two years ago, mapping raw CrowdStrike telemetry to compliance control language required a massive expert system. Today Claude maps it accurately in seconds. This product could not have been built before 2024. Claude Opus 4.x (2025) materially improved the rationale-and-citation quality required for audit-defensible AI output. Workiva's Kansaro acquisition and the Mar 9, 2026 GRC platform launch are the public-company-balance-sheet validation that AI-for-auditors is now real and ownable.

**4. Security and compliance teams are merging — and the CISO is now a discloseable officer**
Post-SolarWinds CISO charges (Oct 2023; securities-fraud claim survived motion to dismiss Jul 2024) and Uber CISO conviction (May 2023), the CISO is personally on the hook for the accuracy of public statements about security controls. The wall between "security tool" and "compliance tool" is collapsing because the people accountable for both are converging — frequently the same person, with the same liability.

---

## Slide 6 — The Solution

### Compliance OS

**The security-telemetry intelligence layer for AuditBoard — starting with CrowdStrike as the first data source, with a multi-vendor architecture from day one.**

```
CrowdStrike Falcon (MVP)  ← multi-vendor expansion: SentinelOne, MS Defender, etc. (V2.0)
  ↓ live telemetry
AI Interpretation Layer (Claude)
  ↓ compliance-mapped evidence
Compliance OS
  ├── Controls & Evidence
  ├── Risk Register (live)
  ├── Findings & Remediation
  └── Framework Dashboard
        ↓ primary deployment for AuditBoard customers
    AuditBoard Connector → AuditBoard tenant  ← future GRC connectors: ServiceNow IRM, Hyperproof, LogicGate
```

**Primary positioning: bridge mode.**
For the ~2,000+ enterprises already running AuditBoard, Compliance OS is the missing automation layer — CrowdStrike evidence flows directly into existing AuditBoard control tests. Customers keep AuditBoard, contracts, training, workpaper conventions. We add the part that hurts.

**Fallback positioning: standalone.**
For enterprises not on AuditBoard (or actively evaluating alternatives — increasingly common as Hg-driven price hikes hit renewal cycles), Compliance OS is a full GRC platform on its own.

**Why bridge-first matters strategically.**
AuditBoard was acquired by Hg Capital in May 2024 (~$3B reported). Hg's playbook is bolt-on M&A to expand ARR ahead of an exit. A visible, paying, customer-validated integration on the AuditBoard ecosystem is the fastest path to being a tuck-in candidate — not a competitor to a PE-backed dealmaker. Bridge-mode is product strategy *and* exit strategy.

**Why we win on the security side, not just the GRC side.**
CrowdStrike Falcon Cloud Security ships compliance dashboards (NIST / CIS / FedRAMP / PCI / HIPAA / GDPR), but they are **vendor-locked, posture-only, and read-only** — they report compliance for *Falcon's view of cloud workloads*. Compliance OS is the layer above:

- **Workflow-grade**, not dashboard-grade — control tests, PBC lists, walkthroughs, owner assignment, finding lifecycle
- **Multi-source**, not single-vendor — orchestrates evidence from CrowdStrike, identity providers, ticketing systems, cloud providers
- **Audit-defensible**, not compliance-themed — provenance chain, immutable evidence, AI-rationale + raw data, re-performance hook (PCAOB AS 1105 / 1215)
- **Cross-framework**, not framework-specific — one control test mapped to SOC 2 + NIST + ISO + PCI simultaneously

---

## Slide 7 — How It Works

### Automated Evidence Collection

The moment an auditor opens a control test, instead of sending a manual request:

1. Compliance OS queries the CrowdStrike API in real time
2. AI interprets the raw data in compliance context
3. Formatted evidence is attached to the control — in 90 seconds

**Before:**
> "Hi, can you pull a CrowdStrike coverage report by Friday?"
> *(3 days later, 4 hours of security analyst time)*

**After:**
> *Control test auto-populated. Status: PASS. 1,847/1,891 endpoints covered. 44 exceptions listed with root cause. Mapped to SOC2 CC6.6, NIST SI-3.*
> *(90 seconds, zero human effort)*

---

### Live Risk Register — Killing the Quarterly Risk Assessment

The legacy risk assessment is a 30-year-old artifact. Once a quarter, a facilitator gathers risk owners in a room (or on Zoom), they vote on likelihood and impact with sticky notes, somebody types the result into AuditBoard, and the board sees a heatmap that is **already 6 weeks stale by the time it is presented.**

This entire workflow is now structurally broken:

- **Regulators have outlawed it.** DORA (live Jan 17, 2025) and NIS2 (transposed Oct 2024) require *continuous* ICT risk management. Quarterly assessment cycles are mathematically incompatible with continuous obligations.
- **The board is personally liable for it.** *Caremark / Marchand / Boeing* duty of oversight requires actively monitored mission-critical risk. Quarterly snapshots are not oversight; they are retrospective reporting.
- **The signal exists already.** CrowdStrike knows about every relevant threat in real time. That signal never reaches the risk register today.
- **Opinion-scored risk is not defensible.** When the SEC asks "what is your basis for this rating in the 10-K?", *"we workshopped it in March"* is not an answer.

**Compliance OS replaces this entire workflow.**

| Legacy quarterly process | Compliance OS continuous process |
|---|---|
| Facilitator workshop, sticky-note voting | Event-driven, telemetry-grounded |
| "Ransomware Risk: High" (opinion) | "Ransomware Risk: HIGH — 47 unpatched endpoints with the active CVE, 3 peer breaches this month, CrowdStrike blocked matching intrusion last week" |
| Static artifact, 90 days stale | Live; updates within 5 minutes of new signal |
| Risk owner notified at quarter-end | Risk owner notified at moment of change |
| Board sees retrospective heatmap once per quarter | Board portal shows current state any business day |
| "Trust us" defensibility | Every score change carries source data, AI rationale, and timestamp — discoverable, auditable, retained 7 years |

**End-to-end example:**

```
CrowdStrike: Critical detection — ransomware behavior on finance server

Compliance OS (within 5 minutes):
→ Risk "Ransomware / Malware" updated: Likelihood HIGH (was Medium)
→ Evidence attached: detection ID, affected asset, timeline, ATT&CK technique IDs
→ Risk owner notified: VP Finance, CISO
→ Related controls flagged for re-testing (CC7.2, NIST DE.CM)
→ Regulatory obligations assessed: HIPAA breach notification clock not yet triggered
→ Board portal updated immediately — no waiting for the next quarterly meeting
→ Audit committee chair sees the change on their next login, with full provenance
```

**The quarterly risk assessment is dead. We are the thing that kills it.**

> **Scope clarifier (because investors will ask).** This kills the *cyber* risk assessment specifically — that is where queryable real-time telemetry exists today. The same model extends to any risk category with live signal: **cloud and identity (V2.0)**, **third-party security (V2.5)**, eventually overlapping with **financial controls** (Workiva's wedge — different vendor, validates the architectural pattern). Strategic risk, reputational risk, geopolitical risk, and other pure-judgment categories remain workshop work; we do not claim to obsolete them. The queryable-telemetry portion of a Fortune 500 risk register is already **~50–60%** of the total — that is the share moving from periodic to continuous, and that is the share we win.

---

### Closed Remediation Loop

```
Audit finding created in Compliance OS
  → Ticket auto-created for security team
  → CrowdStrike issue tracked
  → When resolved: finding auto-closed with evidence
  → Full audit trail preserved
```

---

### Audit-Grade Evidence Chain

Every artifact is captured with the provenance an external auditor needs to rely on it:

```
Evidence record
  ├── Source system + API endpoint + query
  ├── Collection timestamp (UTC, immutable)
  ├── Raw payload (hash-pinned, retained 7 years)
  ├── AI interpretation + prompt version + model ID
  ├── Control mapping (framework, control ID, version)
  ├── Auditor review state (pending / approved / overridden)
  └── Re-performance hook (one-click re-query against live data)
```

This is what allows a Big 4 reviewer to sign the workpaper. **The AI summary is convenience; the raw data + provenance chain is the evidence.**

---

## Slide 8 — Demo

### The 90-Second Demo

| Step | What They See |
|---|---|
| Open control test | Empty — waiting for evidence |
| Click "Sync from CrowdStrike" | Progress indicator |
| 90 seconds later | Control test fully populated |
| Evidence shows | Coverage %, exceptions, AI summary, raw data |
| Control status | Auto-set PASS or FAIL |
| If FAIL | Finding auto-created, assigned, deadline set |

**The contrast sells itself.** The auditor knows this used to take 3 days and a senior analyst. Now it takes 90 seconds.

---

## Slide 9 — Product

### Core Modules

**Controls & Evidence**
- 30+ pre-mapped frameworks (SOC2, NIST, PCI-DSS, HIPAA, ISO27001, CMMC)
- Continuous automated testing — not just at audit time
- AI-written evidence summaries auditors can use directly
- Full raw data attached for deep review

**Risk Register**
- Live risk scores driven by security telemetry
- FAIR-based dollar risk quantification
- Threat intelligence context from CrowdStrike
- Board-ready risk reports generated by AI

**Findings & Remediation**
- Auto-created from failed control tests
- Bi-directional sync with security team workflow
- SLA tracking and escalation
- Closed automatically when CrowdStrike confirms fix

**Framework Dashboard**
- **MITRE ATT&CK coverage heatmap** — visualizes detection coverage across the 14 ATT&CK tactics and ~200 techniques (the public knowledge base of how real-world attackers behave, maintained by MITRE). For every technique, we show whether the connected security platform has a detection, when it last fired, and which compliance controls reference it. Three colors:
  - **Green** — detection exists, exercised in the last 90 days
  - **Yellow** — detection exists, not exercised recently
  - **Red** — no detection in the customer's environment
  This is the single chart a CISO can put in front of the board to answer *"how complete is our detection coverage against the threats actually being used?"* — and it doubles as auditor-defensible evidence that detection controls (NIST CSF DE.CM, SOC 2 CC7.2) are operating across the threat landscape, not just on paper.
- **Compliance posture score by framework** — single score per framework (SOC 2: 94%, NIST: 87%, etc.)
- **Trend over time** — posture deltas week-over-week, surfacing degradation before audit cycles
- **Peer benchmarking** — anonymized comparison against same-industry, same-size cohort

**Integrations**
- **CrowdStrike Falcon** (required at MVP — primary data source); **SentinelOne, Microsoft Defender for Endpoint** on V2.0 roadmap (multi-EDR is a deliberate design choice, not an aspiration)
- **AuditBoard** (optional bridge connector — push evidence to existing tenant); **ServiceNow IRM, Hyperproof, LogicGate** on roadmap
- Okta, Jira, ServiceNow ITSM (roadmap)

---

### Risk Domain Coverage — staged expansion path

Each new connector unlocks a new risk domain on the live-register model. The expansion is the same architectural pattern (queryable telemetry → AI interpretation → live risk + control update) applied to a new data source. **The connectors are the strategy.**

| Wave | Risk domain unlocked | Connectors that unlock it | Compliance OS version |
|---|---|---|---|
| **1 (MVP)** | Endpoint security, vulnerability, malware, insider threat | CrowdStrike Falcon | V1.0 |
| **2** | Identity & access risk, privilege creep, MFA coverage gaps | Okta, Microsoft Entra ID | V1.5 |
| **3** | Multi-vendor endpoint (EDR concentration risk mitigation) | SentinelOne, MS Defender for Endpoint | V2.0 |
| **4** | Cloud security posture, IaaS/PaaS misconfigurations | AWS CloudTrail, Azure Monitor, GCP Audit | V2.0 |
| **5** | Third-party / vendor security risk | BitSight, SecurityScorecard, SOC 2 portal connectors | V2.5 |
| **6** | Data security posture (DSPM signals) | Cyera, Varonis, vendor APIs | V3.0 |
| **7** | AI / model risk (board agenda item in 2026) | AIDR-class platforms, model registries | V3.0+ |

**Out of scope by design** — strategic, reputational, geopolitical, legal, and HR risk remain judgment / intelligence-driven. We do not pretend telemetry exists for these. Workiva already owns the financial-controls wedge (Sustain.Life, Kansaro, March 2026 GRC launch); we do not enter that lane.

---

## Slide 10 — Competitive Landscape

### Why Nothing Else Does This

| Company | What They Do | Why It's Different | 2025–2026 Position |
|---|---|---|---|
| **AuditBoard** | Enterprise GRC platform | No security telemetry integration; manual evidence only | Hg Capital portfolio (~$3B, May 2024); growth via PE bolt-ons |
| **Workiva** | Connected reporting + AI-Powered GRC platform (launched **Mar 9, 2026** at IIA Great Audit Minds) | AI evidence analysis and control-health dashboards — but **70+ connectors are financial-system-oriented** (Oracle, Salesforce, Workday, BlackLine, Persefoni); **no native CrowdStrike or security-telemetry connectors** | Public ($WK), acquired **Kansaro** (AI workpaper automation for auditors, founders Laird/Joubert/Newcomer) and **Sustain.Life** ($100M, Jun 2024). Now the most credible AI-GRC challenger to AuditBoard. |
| **CrowdStrike Charlotte AI** | AI SOC assistant | Security-only, no compliance output, no GRC layer | GA mid-2024; expanded with agentic capabilities 2025 |
| **CrowdStrike Falcon Cloud Security (CSPM) + Exposure Management + FileVantage** | Compliance dashboards against NIST / CIS / FedRAMP / PCI-DSS / HIPAA / GDPR; Drata integration maps Falcon vulnerability data to one specific test (DCF-18) | **Vendor-locked and cloud-posture-only.** Reports compliance for *Falcon's view of your environment*. No risk register, no policy management, no PBC workflow, no multi-source orchestration, no Big-4-grade workpaper export. Spring 2026 release flagged "expanded governance" — direction of travel is real but current product is nowhere near full GRC. | Spring 2026 platform release explicitly mentions "expanded governance"; AIDR (GA Dec 2025) extended platform to AI security with governance framing — yellow flag on trajectory |
| **CardinalOps** | Detection engineering | Focuses on SIEM rule coverage, not GRC | Niche; partner not competitor |
| **Vanta** | Compliance automation, mid-market origin | Pulls thin signals (MFA on? AV installed?); not deep telemetry; weakest at custom enterprise frameworks | Reported ~$2.45B valuation (2024 raise); pushing upmarket but enterprise IT-audit fit is unproven |
| **Drata** | Compliance automation, similar to Vanta | Same architectural limit — agent-based posture checks, not platform telemetry | Acquired Stride Security (Sept 2024) for risk management; expanding into TPRM |
| **Secureframe** | Compliance automation | Same category; weaker enterprise penetration | Mid-market |
| **ServiceNow IRM** | Enterprise GRC inside ServiceNow | Massive, expensive, 12-month implementation; no native security telemetry | Strong in F500 but slow to evolve |
| **Hyperproof / LogicGate / Onspring** | Mid-market GRC | No security telemetry layer | Compete with AuditBoard, not us |

**The wedge is specific and defensible against every name in this table:**

- **Workiva**: deep on financial reporting and now AI auditor workflow, but went **broad** across reporting + sustainability + GRC. Their connector library is built for the controller's office, not the SOC. They don't speak CrowdStrike.
- **Vanta / Drata / Secureframe**: agent-based posture checks. They know *if* MFA is on. We know *what threats it blocked, on which population, with what exception rate, mapped to which control under which framework, with audit-grade provenance.*
- **AuditBoard / ServiceNow IRM / Hyperproof**: GRC platforms that wait for evidence to be uploaded. They are the system of record; we are the system of *intake* that fills them.

### Defensibility

1. **Data moat** — control mapping intelligence improves with every customer
2. **Workflow lock-in** — auditors run their audit cycles through us, not AuditBoard
3. **Framework depth** — 30+ frameworks pre-mapped takes years to replicate
4. **AI training** — evidence quality improves as we see more audit feedback

---

## Slide 11 — How We Win Against the Two Most Likely Native-Build Threats

> Two adjacent platforms could in principle build what we build. Investors will ask about both.
> **CrowdStrike from below** — security-platform side extending compliance dashboards into full GRC.
> **Workiva from above** — AI-GRC side extending Kansaro (financial-audit AI) into cyber audit.
> We hold the wedge between them. Each has structural barriers that take years to overcome, and each has an M&A pattern that says "buy the specialist." We are the specialist.

### The symmetry

```
              CrowdStrike (security depth)
                       │
                       │  "I have Falcon data — here are
                       ▼   compliance dashboards on it."
            ┌─────────────────────────────┐
            │       Compliance OS         │
            │  Workflow + multi-source +  │
            │  audit-defensible +         │
            │  cross-framework            │
            └─────────────────────────────┘
                       ▲
                       │  "I have audit workflow + AI —
                       │   I just need security data."
                       │
                  Workiva (GRC + audit-AI breadth)
```

CrowdStrike comes from below — owns the security data plane, lacks the audit workflow. Workiva comes from above — owns the audit workflow, lacks the security data plane. We are the only platform built around the wedge that connects them, as the entire product, not as a feature inside someone else's product.

---

### Threat A — CrowdStrike extends compliance natively

CrowdStrike's compliance footprint is real — Falcon Cloud Security CSPM (NIST / CIS / PCI / HIPAA / GDPR posture), Exposure Management compliance dashboards, FileVantage FIM ("Compliance, Simplified"), and the Drata + Falcon Exposure Management integration that maps vulnerability data to one specific test (DCF-18). Spring 2026's release explicitly markets "expanded governance"; AIDR (GA Dec 2025) extended Falcon to AI security with governance framing.

Categorically different from what we do. They report compliance for *Falcon's view of the customer's environment*. They do not run the audit cycle, orchestrate evidence across vendors, or produce artifacts an external auditor can attach to a workpaper.

**Seven structural reasons CrowdStrike can't easily close this:**

| # | Win condition | Why CrowdStrike can't easily close it |
|---|---|---|
| 1 | **Workflow-grade, not dashboard-grade** | We run PBC lists, walkthroughs, control-test lifecycle, finding-to-closure, workpaper export. CrowdStrike's compliance is a view inside a security platform — our product is a different DNA, built for a different user. |
| 2 | **Multi-source orchestration** | We pull from CrowdStrike + identity (Okta) + ticketing (Jira / ServiceNow) + cloud (CloudTrail) + (V2.0) other EDRs. CrowdStrike compliance can only ever see CrowdStrike data — architecturally. The moment a customer asks about a non-Falcon system, our wedge becomes inevitable. |
| 3 | **Cross-framework many-to-many mapping** | One control test satisfies SOC 2 + NIST + ISO + PCI + HIPAA + CMMC simultaneously. CrowdStrike's mapping is one-to-one (Falcon → framework). Many-to-many is a data moat that takes years and improves with every customer. |
| 4 | **Audit-defensible provenance chain** | Source + query + timestamp + raw payload (hash-pinned, 7-year retention) + AI prompt + model version + re-performance hook. Defensible under PCAOB AS 1105 / 1215. CrowdStrike dashboards are convenience views — auditors cannot attach them to workpapers. |
| 5 | **Different buyer, different budget center** | CrowdStrike sells to CISO. We sell to CAE / CCO / IT Audit Manager / external Big 4 auditor. Different procurement motion. CrowdStrike has no sales organization into the audit committee — building one takes years. |
| 6 | **Big 4 methodology embedment** | Audit firms adopt our workpaper format and methodology toolkit (precedent: Caseware, MindBridge, AuditFile). They cannot adopt the *auditee's security vendor* as audit methodology — independence rules forbid it. Institutional moat no security vendor can replicate. |
| 7 | **Vendor-neutrality is a product claim, not a marketing claim** | Post the Jul 19, 2024 Falcon outage, single-vendor lock-in is a board-level conversation. We architecturally cannot be locked to CrowdStrike. CrowdStrike compliance architecturally cannot be anything *but* locked to CrowdStrike. The asymmetry sharpens every quarter. |

---

### Threat B — Workiva extends Kansaro into cyber audit

Workiva is the most credible AI-GRC challenger. They acquired **Kansaro** (AI workpaper automation for auditors), launched the **AI-Powered Workiva GRC Platform on Mar 9, 2026**, and have a public-company balance sheet behind both. Natural objection: *why won't Workiva just extend Kansaro into cyber too?*

**Seven structural barriers say they will buy the specialist (us, or someone like us) rather than build:**

| # | Structural barrier | What it means |
|---|---|---|
| 1 | **Wrong evidence architecture** | Kansaro is document-centric — PDF splitting, 10-K scanning, GL tick-and-tie. Cyber audit needs streaming live API telemetry, population queries, ATT&CK mapping. Different data plane, different team. |
| 2 | **Wrong connector ecosystem** | Workiva's 70+ connectors are all financial systems (Oracle, SAP, Workday, BlackLine, Persefoni). Zero security telemetry. One major EDR connector with proper rate-limiting, pagination, retry is 6–9 months of engineering by a team they don't have. |
| 3 | **Wrong buyer inside the audit firm** | Big 4 separate assurance (CPA-track) from risk / IT audit (CISA-track). Workiva sells to assurance via Kansaro. Cyber audit reports through a different partner, often a different P&L. No relationships. |
| 4 | **Wrong framework universe** | Financial audit = GAAP / IFRS / SOX 404 ITGCs (narrow, slow-moving). Cyber audit = SOC 2 / NIST / ISO / PCI / HIPAA / CMMC / DORA / NIS2 / FedRAMP (broad, dynamic, requires constant maintenance). No framework-mapping team for this. |
| 5 | **M&A pattern says buy, don't build** | Kansaro (AI workpapers), Sustain.Life ($100M, ESG), ParsePort + Arelle (XBRL tagging), AuditNet (GRC). Pattern is unambiguous — Workiva enters adjacent verticals via acquisition. **Kansaro literally maps our acquisition path.** Compliance OS is the obvious "Kansaro for IT/security audit." |
| 6 | **Cyber is roadmap priority 3–4, not 1** | Immediate post-March-2026 focus: integrate Kansaro deeper, expand the GRC platform, deepen Sustain.Life. Cyber audit is a future phase. That gives us a window to be the visible target when their M&A team gets there. |
| 7 | **Domain credibility gap is years deep** | Cyber auditors speak ATT&CK, CVE, EDR, SOC. Workiva product team has zero domain experience. Big 4 IT audit adoption requires earned trust over years — Workiva would be entering as the financial-reporting vendor pivoting in. Easier to acquire credibility than build it. |

**The acquisition implication is the kicker.** The Kansaro deal *is* the precedent. The next vertical Workiva will want to own — after current acquisitions mature — is AI-for-cyber-auditors. They will not build it; their entire pattern says they buy. **That makes Compliance OS one of perhaps three companies in the world they will want to acquire when they get there.**

---

### Where the gap could close — and how we mitigate (combined)

| Risk | Source | What it looks like | Mitigation |
|---|---|---|---|
| CrowdStrike acquires a GRC startup | Threat A | Falcon adds a workpaper-grade compliance module via M&A | Be acquired *first*. Our 2027 acquisition-readiness clock applies here too. |
| Charlotte AI extends into compliance assistant | Threat A | Compliance-skin shipped natively in 2026–2027 | Depth advantage — provenance chain, cross-framework mapping, Big 4 references take 18+ months to replicate. |
| Drata + Falcon integration deepens beyond DCF-18 | Threat A | Dozens of mappings, becomes the mid-market default | Cede mid-market posture-checks; differentiate on enterprise depth (AS 1215 retention, population testing, audit-committee features). |
| Workiva acquires a competing security-telemetry-to-GRC startup before us | Threat B | Workiva announces the cyber-audit equivalent of Kansaro | Be visible — publish technical content on the wedge, attend IIA / ISACA / RSA where Workiva's M&A team scouts targets, get to first paying customers fast. |
| Workiva builds a thin native CrowdStrike connector | Threat B | One EDR connector ships in a 2026–2027 release | Depth advantage — provenance chain, multi-vendor architecture, Big 4 methodology lock-in are not feature parity items. |
| Both sides converge on a "good enough" mid-market answer (Drata + Workiva ecosystem) | A + B | Combined effect makes the mid-market crowded | Win at the enterprise tier where Big 4 audit firms drive procurement. The PCAOB-defensible workpaper requirement filters out the mid-market posture players. |

---

### Concrete moves we are making now

1. **AuditBoard partner program engagement** (PRD Phase 5) — primary acquisition path; the Hg-portfolio deal closes the AuditBoard-from-above lane
2. **CrowdStrike marketplace listing by Q4 2026** — partner positioning; surfaces us on CrowdStrike's M&A radar
3. **Pitch frames us as "partners with both"** — *"Falcon dashboards tell you about cloud posture; Workiva does financial-audit AI; we are the security-telemetry-to-audit-evidence layer between them."* Never "vs" either.
4. **Technical content piece on the AS 1105 depth gap** — *"Mapping Falcon Exposure Management vulnerability data to PCAOB AS 1105–defensible audit evidence: what Drata's DCF-18 mapping does and does not cover."* Positions us as the deep-end player.
5. **First Big 4 audit-firm reference customer** — a single CrowdStrike-using Big 4 IT audit practice running our workpapers invalidates *both* "CrowdStrike compliance is enough" *and* "Workiva will extend Kansaro to cyber" for every enterprise prospect for the rest of the year.
6. **Visibility at IIA, ISACA, and RSA** — these are the conferences where Workiva's product team and CrowdStrike's corp dev recruit acquisition targets. Be on the floor and on stage.

---

## Slide 12 — The Market

### Who has this problem

- **~2,000+** enterprises use AuditBoard (~50% of Fortune 500). Acquired by Hg Capital in May 2024 at a reported ~$3B valuation — now in active growth mode under PE ownership.
- **~30,000** subscription customers on CrowdStrike Falcon (FY26 reporting, fiscal year ending Jan 2026)
- Overlap concentrated in Fortune 500, regulated mid-market, and US federal contractors

### Regulatory tailwind accelerating urgency

| Regulation | Requirement | Status as of 2026 |
|---|---|---|
| **SEC Cyber Disclosure Rule** (Item 1.05 8-K, Reg S-K Item 106) | Report material cyber incident within 4 business days; describe board oversight in 10-K | Effective Dec 18, 2023 (large filers); June 15, 2024 (smaller reporting cos). Enforcement actions emerging. |
| **DORA** (EU Reg 2022/2554) | Continuous ICT risk controls for ~22,000 EU financial entities + ICT third parties | **Live since Jan 17, 2025**. First supervisory dialogues underway 2025–2026. |
| **NIS2 Directive** (EU 2022/2555) | Ongoing risk management, incident reporting, board accountability with personal liability | Transposition deadline **Oct 17, 2024**. Member-state enforcement ramping through 2025–2026. |
| **CMMC 2.0** (32 CFR Part 170) | Tiered security posture evidence for defense contractors handling FCI/CUI | **Final Rule published Oct 15, 2024**. Phased contract incorporation began 2025; full incorporation by 2028. |
| **NIST CSF 2.0** | Adds GOVERN function — board oversight is part of the framework, not a wrapper | Released **Feb 26, 2024**. Becoming the de facto baseline cited by regulators and insurers. |
| **PCI-DSS v4.0.1** | Stronger authentication, continuous controls, customized approach | Mandatory since **Mar 31, 2024**; new "future-dated" requirements enforceable from **Mar 31, 2025**. |
| **EU AI Act** | Risk-tiered obligations, governance and transparency for AI systems including those used in compliance | Entered force **Aug 1, 2024**; phased application through 2026 (general-purpose AI rules from Aug 2025). |
| **HIPAA Security Rule update** | NPRM proposes specific technical controls, mandatory MFA, encryption, vulnerability scanning | NPRM published **Dec 2024**; final rule expected 2025–2026. |

**Every new regulation increases the cost of the manual, screenshot-based compliance process that exists today.** Six of the eight items above did not exist in their current form three years ago.

### Market sizing

| Segment | Size | Source |
|---|---|---|
| Global GRC software market (2025) | ~$60B | Industry analyst consensus (Gartner IRM, Forrester, Mordor) |
| Integrated risk management (IRM) software, narrower | ~$8–12B | Gartner Magic Quadrant for IRM |
| AI in GRC CAGR (2025–2030) | ~22–25% | MarketsAndMarkets, Mordor Intelligence |
| Security compliance automation (sub-segment) | ~$5B+ | Vanta, Drata, Secureframe at unicorn valuations validate |
| Addressable wedge (CrowdStrike + AuditBoard overlap) | ~$800M ARR opportunity at $50K ACV | Bottoms-up: ~16,000 enterprise targets × 10% capture |

---

## Slide 13 — Business Model

### Pricing

| Tier | Price | Who |
|---|---|---|
| Starter | $2,000/month | Up to 500 endpoints, 1 framework |
| Professional | $5,000/month | Up to 2,500 endpoints, all frameworks, AuditBoard connector |
| Enterprise | $15,000+/month | Unlimited endpoints, custom frameworks, dedicated support |

### Unit Economics

- Average ACV target: **$50,000**
- Estimated CAC: **$15,000** (channel-led)
- Payback period: **4 months**
- Gross margin target: **80%+** (SaaS, AI inference cost manageable at scale)

### Revenue Milestones

| Milestone | Target |
|---|---|
| First paying customer | Month 3 |
| $10K MRR | Month 6 |
| $100K MRR | Month 18 |
| Series A ready | Month 24 |

---

## Slide 14 — Go-To-Market

### Phase 1 — Design Partners (Months 1–3)

Target: 3 enterprises currently using both CrowdStrike and AuditBoard.
Ask: $5,000–$10,000 to build with us. We shape the product around their audit cycle.
Find them: LinkedIn search "AuditBoard" + "CrowdStrike" in profile.

### Phase 2 — Channel (Months 4–12)

**Big 4 audit and advisory firms** (Deloitte, PwC, KPMG, EY) are the highest-leverage channel for two distinct reasons:

1. **Advisory side** — they implement AuditBoard for hundreds of enterprise clients and recommend CrowdStrike alongside it. They feel the integration gap on every engagement.
2. **Audit side** (the larger prize) — their *own* IT audit teams burn 30–40% of fieldwork hours on PBC chase and manual evidence formatting. A platform that compresses that time directly protects partner margin under fee compression. This is not a "nice to have" for them; it is methodology survival.

Approach:
- **Channel program** — referral or resell with 20% fee for advisory-side deals
- **Audit firm site licenses** — direct sale to the Big 4 IT audit practice itself, used across their client base as part of their methodology toolkit (precedent: Caseware, MindBridge, AuditFile)

**MSSPs** managing CrowdStrike for multiple clients — Compliance OS gives them a compliance story they can sell to their clients alongside security services.

### Phase 3 — Marketplace (Month 12+)

- AuditBoard marketplace listing → direct access to ~2,000+ enterprise customers
- CrowdStrike marketplace listing → direct access to ~30,000 enterprise customers
- Both channels validate us as a real integration, not a competitor

---

## Slide 15 — Acquisition Thesis

This is built to be acquired. There is a clear primary buyer with timing pressure, and a credible fallback set if that buyer doesn't move.

### Primary target: AuditBoard (Hg Capital portfolio)

**This is the buyer to design the company around.**

- Hg acquired AuditBoard in **May 2024 at a reported ~$3B valuation**. PE hold periods typically run 5–7 years, putting AuditBoard's exit window at roughly **2028–2031**.
- Hg's playbook in software is unambiguous: bolt-on M&A to expand the ARR base, modernize the product (especially AI and integrations), and exit at a higher multiple. Compliance OS is precisely the kind of bolt-on this playbook hunts for — adjacent product, paying customers, complementary integration into the core platform.
- AuditBoard's structural product gap is real-time security telemetry. They cannot build this faster than we can ship it because they don't own the underlying data plane (CrowdStrike does).
- Bridge-mode positioning means we arrive on Hg's M&A radar already integrated with their portfolio company, with their customers using us, paying for us, and validating the integration. That is the strongest possible setup.

**Implied timeline pressure on us**: to be on the M&A list before AuditBoard's exit, Compliance OS needs material ARR (~$5M+) and visible customer overlap by **~2027**. That sets the clock on Series A and on the first 50 customers.

**Risk on this path**: Hg may acquire a competing compliance-automation player first (Hyperproof, Onspring, lower-tier of Vanta/Drata), or AuditBoard may ship a native CrowdStrike connector internally before we hit material ARR. Both reduce — though do not eliminate — our value as a target.

---

### Fallback acquirers (if AuditBoard/Hg doesn't move)

Each of these has independent, current strategic motivation. Multiple credible buyers in adjacent positions = auction dynamic at exit even if Hg passes.

#### Workiva ($WK) — highest-conviction secondary
- Public company; just launched the **AI-Powered Workiva GRC Platform on Mar 9, 2026**, declaring AI-driven evidence analysis and intelligent control-health dashboards the new center of GRC
- Acquired **Kansaro** (AI workpaper automation for auditors) — the explicit precedent that Workiva will pay for category-specific AI audit tooling
- Acquired **Sustain.Life** ($100M, Jun 2024) for ESG; **OneCloud** for iPaaS; **AuditNet** to extend GRC
- Structural gap: 70+ connectors are financial-system-oriented (Oracle, Salesforce, Workday, BlackLine, Persefoni). **No native CrowdStrike or security-telemetry connector.** Compliance OS is the closest thing on the market to "Kansaro for IT/security audit" — same acquisition logic, different vertical.

#### CrowdStrike
- Extends Falcon from CISO budget into CFO / CAE / CCO budget — a budget Falcon does not currently address
- Extends Charlotte AI into GRC use cases beyond the SOC
- Active acquirer: **Adaptive Shield** (Nov 2024, ~$300M, SSPM), **Flow Security** (Mar 2024, ~$200M, DSPM), **Bionic** (Oct 2023, ~$350M, ASPM), **Humio** (Feb 2021, ~$400M, log management)
- Compliance OS fits the same tuck-in pattern

#### ServiceNow
- Competes with AuditBoard in GRC/IRM via the IRM module
- Acquiring Compliance OS accelerates the security-evidence story without internal build cycles
- Direction: AI-led acquisitions and platform extension; security posture data is the missing layer

#### Palo Alto Networks
- Active consolidator with explicit platform-consolidation thesis: **Talon** (Nov 2023, $625M, enterprise browser), **Dig Security** (Nov 2023, ~$400M, DSPM), **QRadar SaaS from IBM** (May 2024 announcement)
- Compliance layer is the gap CrowdStrike has not filled — owning it creates direct competitive differentiation

#### SentinelOne
- Acquired **PingSafe** (Jan 2024, ~$100M, CNAPP)
- Same thesis as CrowdStrike but earlier in the platform-extension curve; needs the compliance layer to compete on board-level value

#### Wiz / Snyk / other CNAPP and DSPM platforms
- Compliance OS framework-mapping engine is the layer they would need to enter the GRC market

---

## Slide 16 — Ask

### What we're building toward

**Seed round: $1.5M**

Use of funds:
- 60% Engineering (2 engineers, 18 months)
- 20% Go-to-market (channel partnerships, Big 4 relationships)
- 20% Infrastructure and AI costs

**Milestones this funding achieves:**
- MVP live with 3 paying design partners
- AuditBoard and CrowdStrike marketplace listings
- $100K ARR
- Series A ready with 12-month runway

---

*Compliance OS — Turning security telemetry into compliance intelligence.*

> **Naming convention used in this deck:** Specific vendor names (CrowdStrike, AuditBoard, Workiva, etc.) are used throughout for investor impact — concrete anchors are more persuasive than abstract archetypes in a pitch context. The product itself is multi-vendor by design: CrowdStrike + AuditBoard are the *first* connectors, with SentinelOne, MS Defender, ServiceNow IRM, Hyperproof, and others on the V2.0 roadmap. The README and PRD (public-facing / partner-shareable) use generic terminology where appropriate.

---

# Appendix — Buyer Personas in Depth

> The summary table on Slide 4 condenses three personas. The full first-person memos below are the source material — useful for sales conversations, customer-development interviews, and diligence packets where the investor or partner wants to see the underlying argument and regulatory references in full.

---

## Appendix A — The Auditor's View

> *Written from the desk of a senior IT audit manager at a Big 4 firm.*

### What I actually do for a living

For every SOX, SOC 2, or ISO engagement, my team executes the same loop on roughly **40–60 IT General Controls** per client: logical access, change management, computer operations, and — increasingly — endpoint security and vulnerability management.

For each control we are required by professional standards to:

1. **Understand the control** — walkthrough with the control owner
2. **Test design effectiveness** — does the control, as described, address the risk
3. **Test operating effectiveness** — sample populations and re-perform
4. **Document evidence** — sufficient, appropriate, retained for **7 years** (SOX) under **PCAOB AS 1215**

Today, step 3 is where the engagement bleeds. We send the client a **PBC list** ("Provided By Client") with 200+ requests. The client's security team responds when they can. Half the artifacts come back in the wrong format. Some are screenshots with no timestamp — which under **PCAOB AS 1105** is borderline insufficient evidence. We sample, because testing the full population is impossible at human speed.

### Three structural problems the profession is hitting

**1. Sampling is no longer defensible when the population is queryable.**
Auditing standards (AS 1105, ISA 500) require *sufficient appropriate evidence*. When the underlying system can return the entire population in seconds, sampling 25 endpoints out of 1,891 starts to look like an audit shortcut, not a methodology choice. PCAOB inspections increasingly flag this.

**2. The talent pipeline has collapsed.**
AICPA candidate volume is at a 20-year low. Big 4 IT audit practices cannot hire fast enough to absorb new regulation (SEC Cyber, DORA, NIS2). Every hour spent reformatting CSVs is an hour not spent on judgment work — the only work that justifies our hourly rate.

**3. Audit fee compression is structural.**
Clients renegotiate every cycle. Partners are asked to deliver the same opinion with 10–15% fewer hours year over year. The only way that math works is automation of evidence collection — the most labor-intensive, least judgment-intensive part of the engagement.

### Why this product hits the auditor where it counts

| What a senior auditor needs | What Compliance OS delivers |
|---|---|
| Sufficient appropriate evidence (AS 1105) | System-of-record telemetry with provenance chain |
| Population testing, not sampling | Every endpoint queried, every exception listed |
| Re-performance capability | Re-run any control test on demand against live data |
| Audit trail retained 7 years (AS 1215) | Immutable evidence store with timestamp, source, and AI rationale |
| Independence preserved | Auditor consumes evidence; never operates client systems |
| Cross-framework efficiency | One control test mapped to SOC 2 + NIST + ISO simultaneously |

**The professional skepticism standard does not go away.** The auditor still reviews the evidence, evaluates the AI summary against the raw data, and signs the workpaper. What changes is that the 80% of the engagement that was clerical becomes the 20% — and judgment work expands to fill the time we just bought back.

### The honest reason Big 4 will adopt this

It is not idealism. It is margin. A platform that cuts 40% of fieldwork hours on the IT side of the engagement preserves partner economics through the next three rounds of fee compression. Whoever owns the bridge between security telemetry and audit evidence becomes embedded in the methodology — and methodology, in this profession, is the moat.

---

## Appendix B — The CISO's View

> *Written from the desk of a Fortune 500 CISO in 2026.*

### The job changed in the last 24 months

Three events reshaped the role:

1. **SEC vs. SolarWinds CISO (Oct 2023)** — first time the SEC named a CISO personally in a securities-fraud action. Securities-fraud claim survived motion to dismiss in July 2024. Every public-company CISO read those filings.
2. **Uber CISO conviction (May 2023)** — Joe Sullivan convicted of federal charges for breach concealment. The legal precedent is now established.
3. **SEC Cybersecurity Disclosure Rule (effective Dec 18, 2023)** — Form 8-K Item 1.05 requires disclosure of a *material* cybersecurity incident within **4 business days** of materiality determination. The CISO is the principal advisor on whether something is material.

### What this means for the daily job

I am no longer just the head of security operations. I am a **discloseable officer of a public company**, with personal exposure on the accuracy of Item 106 disclosures (governance), Item 1.05 8-Ks (incidents), and increasingly D&O-adjacent litigation. My team's CSV exports for the auditor are not just an annoyance — they are part of an evidence chain I may have to defend under oath.

### The structural pressures stacking on top

| Pressure | What it does to me |
|---|---|
| **DORA enforcement (live Jan 17, 2025, EU)** | Continuous ICT risk controls — quarterly artifacts no longer satisfy. Evidence must be ongoing. |
| **NIS2 transposition (deadline Oct 17, 2024)** | EU member states now empowered to fine and disqualify management for inadequate controls. |
| **NIST CSF 2.0 (Feb 2024)** | New GOVERN function — board oversight is now part of the framework itself, not a wrapper around it. |
| **ISC2 workforce study 2024** | 4.8M unfilled cyber roles globally. I cannot solve this with hiring. |
| **Cyber insurance underwriting** | Carriers now require evidence of controls operating, not policy attestations. Renewal questionnaires ask for EDR coverage rates, MFA coverage, backup test cadence — by population, not sample. |
| **CrowdStrike Falcon outage (Jul 19, 2024)** | Boards now ask about vendor concentration risk and the controls around it. I have to answer with data. |
| **Supply-chain incidents** (MOVEit 2023, Snowflake credential incidents 2024 affecting Ticketmaster, Santander, and 160+ others) | Third-party risk is now a board-level conversation, not a procurement checkbox. |

### What I need from a platform

- A **single substrate** that serves audit evidence, board reporting, insurance underwriting, and regulator disclosure — because today I maintain four parallel narratives and they don't reconcile.
- **Materiality assessment support** with a documented methodology — so when I tell my CFO "this is not material," that judgment is defensible.
- **Audit drag eliminated** — every analyst hour I get back from PBC chase is an hour on detection engineering, the only thing that actually reduces incident likelihood.
- **Live posture data my CFO and General Counsel can read directly** — so I am not the bottleneck on every cross-functional risk question.

### What sells me

Not "compliance automation." That language belongs to 2018. What sells me is: *"the same data that proves controls work for the audit committee proves them for the SEC, the cyber insurance carrier, and the regulator — and frees my team to do security work."*

---

## Appendix C — The Board Member's View

> *Written from the desk of an independent director on a Fortune 1000 audit committee.*

### Why I personally pay attention

The duty-of-oversight bar moved. *In re Caremark* (Delaware, 1996) was reinforced by **Marchand v. Barnhill (2019)** and **In re Boeing (2021)**: directors have an affirmative duty to actively oversee mission-critical risks. Cyber, in 2026, is unambiguously mission-critical at every public company.

If a derivative suit follows a material incident, my emails, board materials, and meeting minutes will be discoverable. "Management briefed us quarterly" is not a defense. The plaintiff's bar will ask: *what oversight infrastructure existed, what data did the board look at, and how often.*

### What current regulation forces onto our agenda

**SEC Reg S-K Item 106** (effective with 10-K filings for fiscal years ending on or after Dec 15, 2023) requires our 10-K to describe:

- Our **processes** for assessing, identifying, and managing material cyber risks
- The **board's oversight** of cyber risk
- **Management's role** and expertise in assessing and managing cyber risk

This language is now reviewed by SEC staff. Boilerplate gets a comment letter.

### The cadence problem

Today, our audit committee sees cyber once a quarter as a 30-slide deck. By the time it is presented, it is 4–6 weeks stale. Between meetings, I have no view at all. If a material incident occurs in week 7 of the quarter, the institutional knowledge I bring to the disclosure conversation is from the *prior* quarter's snapshot.

This is the structural problem the **NACD Director's Handbook on Cyber-Risk Oversight (5th edition, 2023)** flags directly: oversight is continuous, but the data we receive is periodic.

### What I need

- A **read-only board portal** — I can log in any day of the quarter and see current control posture, top risks, and trend
- A **documented oversight trail** — proof I exercised duty-of-care, time-stamped, retained, discoverable on my side rather than only on management's
- **Materiality narrative on demand** — if an Item 1.05 trigger occurs, the board needs a defensible position within hours
- **Peer benchmarking** — am I better, worse, or normal vs. comparable companies, on the controls that matter
- **One platform that also covers AI governance** — because that is the next item being added to my committee's charter

### What this product does for me

It converts "we trust management" into "we have independently observable evidence." That is the difference between a Caremark defense that holds and one that does not.
