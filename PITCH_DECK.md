# Compliance OS — Pitch Deck

> AI-powered compliance intelligence that closes the gap between security telemetry and audit evidence

---

## Slide 1 — The Setup

**Every large enterprise has two groups who both care about security.**

The **Security Team** lives in CrowdStrike. They see every threat, every vulnerability, every misconfigured endpoint in real time. They have the most accurate picture of the organization's security posture that has ever existed.

The **Audit & Compliance Team** lives in AuditBoard. They manage controls, run audits, maintain the risk register, and answer the question every board member asks: *"Are our controls actually working?"*

**These two teams share the same building. Their systems share nothing.**

---

## Slide 2 — The Problem

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

## Slide 2.5 — The Auditor's View

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

## Slide 2.6 — The CISO's View

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

## Slide 2.7 — The Board Member's View

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

---

## Slide 3 — The Market

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

## Slide 4 — The Solution

### Compliance OS

**A full GRC platform powered by live security telemetry — with an optional AuditBoard connector for customers who already use it.**

```
CrowdStrike Falcon
  ↓ live telemetry
AI Interpretation Layer (Claude)
  ↓ compliance-mapped evidence
Compliance OS
  ├── Controls & Evidence
  ├── Risk Register (live)
  ├── Findings & Remediation
  └── Framework Dashboard
        ↓ optional
    AuditBoard Connector
```

**Two ways to deploy:**
1. **Standalone** — replace AuditBoard for IT/security compliance workflows
2. **Bridge mode** — keep AuditBoard, add real-time security evidence automation

---

## Slide 5 — How It Works

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

### Live Risk Register

Risk scores update automatically when CrowdStrike detects significant events:

```
CrowdStrike: Critical detection — ransomware behavior on finance server

Compliance OS:
→ Risk "Ransomware / Malware" updated: Likelihood HIGH (was Medium)
→ Evidence attached: detection ID, affected asset, timeline
→ Risk owner notified: VP Finance, CISO
→ Related controls flagged for re-testing
→ Regulatory obligations assessed: HIPAA breach notification not yet triggered
```

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

## Slide 6 — Product

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
- MITRE ATT&CK coverage heatmap
- Compliance posture score by framework
- Trend over time
- Peer benchmarking

**Integrations**
- CrowdStrike Falcon (required — primary data source)
- AuditBoard (optional — push evidence to existing platform)
- Okta, Jira, ServiceNow (roadmap)

---

## Slide 7 — Demo

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

## Slide 8 — Business Model

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

## Slide 9 — Go-To-Market

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

- AuditBoard marketplace listing → direct access to 2,000 customers
- CrowdStrike marketplace listing → direct access to 29,000 customers
- Both channels validate us as a real integration, not a competitor

---

## Slide 10 — Competitive Landscape

### Why Nothing Else Does This

| Company | What They Do | Why It's Different | 2025–2026 Position |
|---|---|---|---|
| **AuditBoard** | Enterprise GRC platform | No security telemetry integration; manual evidence only | Hg Capital portfolio (~$3B, May 2024); growth via PE bolt-ons |
| **CrowdStrike Charlotte AI** | AI SOC assistant | Security-only, no compliance output, no GRC layer | GA mid-2024; expanded with agentic capabilities 2025 |
| **CardinalOps** | Detection engineering | Focuses on SIEM rule coverage, not GRC | Niche; partner not competitor |
| **Vanta** | Compliance automation, mid-market origin | Pulls thin signals (MFA on? AV installed?); not deep telemetry; weakest at custom enterprise frameworks | Reported ~$2.45B valuation (2024 raise); pushing upmarket but enterprise IT-audit fit is unproven |
| **Drata** | Compliance automation, similar to Vanta | Same architectural limit — agent-based posture checks, not platform telemetry | Acquired Stride Security (Sept 2024) for risk management; expanding into TPRM |
| **Secureframe** | Compliance automation | Same category; weaker enterprise penetration | Mid-market |
| **ServiceNow IRM** | Enterprise GRC inside ServiceNow | Massive, expensive, 12-month implementation; no native security telemetry | Strong in F500 but slow to evolve |
| **Hyperproof / LogicGate / Onspring** | Mid-market GRC | No security telemetry layer | Compete with AuditBoard, not us |

**The gap is specific**: nobody translates deep CrowdStrike telemetry into compliance evidence and live risk intelligence. Vanta knows if antivirus is installed. We know if it is actually working, what threats it blocked, what the population coverage is, and what an external auditor can rely on as evidence under PCAOB AS 1105.

### Defensibility

1. **Data moat** — control mapping intelligence improves with every customer
2. **Workflow lock-in** — auditors run their audit cycles through us, not AuditBoard
3. **Framework depth** — 30+ frameworks pre-mapped takes years to replicate
4. **AI training** — evidence quality improves as we see more audit feedback

---

## Slide 11 — Why Now

Four forces converging in 2025–2026:

**1. Regulatory pressure at a structural inflection**
SEC Cyber Disclosure (live since Dec 2023), DORA (live since Jan 17, 2025), NIS2 (transposition deadline Oct 17, 2024), CMMC 2.0 (Final Rule Oct 15, 2024), NIST CSF 2.0 (Feb 2024), PCI-DSS v4.0.1 (full enforcement Mar 31, 2025), EU AI Act (in force Aug 2024) — all require **continuous demonstrable controls**, not annual audits. The manual screenshot-and-CSV process is mathematically incompatible with the new compliance posture cadence.

**2. The 2024–2025 incident wave permanently raised the bar**
- **Change Healthcare ransomware (Feb 2024)** — UnitedHealth-owned, BlackCat ransomware, ~$2.9B+ direct cost reported, disrupted ~one-third of US healthcare claims processing. Triggered HHS HIPAA enforcement focus.
- **Snowflake credential incidents (May–Jul 2024)** — ~165 customer environments compromised via stolen credentials per Mandiant; Ticketmaster, AT&T, Santander, LendingTree among confirmed victims. Reframed third-party risk for every board.
- **CrowdStrike Falcon outage (Jul 19, 2024)** — single faulty content update grounded ~8.5M Windows endpoints globally. Delta lawsuit and others created the precedent question: who is liable for security-vendor reliability, and how is it evidenced.
- **MOVEit (CL0P, 2023, still litigating in 2025)** — 2,700+ orgs, 95M+ records — set the template for vulnerability-to-extortion at scale.

Each event made *evidence of working controls* a board-level demand, not a back-office artifact.

**3. AI makes the translation layer possible**
Two years ago, mapping raw CrowdStrike telemetry to compliance control language required a massive expert system. Today Claude maps it accurately in seconds. This product could not have been built before 2024. The launch of Claude Opus 4.x (2025) materially improved the rationale-and-citation quality required for audit-defensible AI output.

**4. Security and compliance teams are merging — and the CISO is now a discloseable officer**
Post-SolarWinds CISO charges (Oct 2023; securities-fraud claim survived motion to dismiss Jul 2024) and Uber CISO conviction (May 2023), the CISO is personally on the hook for the accuracy of public statements about security controls. The wall between "security tool" and "compliance tool" is collapsing because the people accountable for both are converging — frequently the same person, with the same liability.

---

## Slide 12 — Acquisition Thesis

This is built to be acquired. Here's why multiple buyers want it.

### CrowdStrike
- Makes Falcon data indispensable to compliance buyers — extends the platform from CISO budget into the CFO / CAE / CCO budget
- Extends Charlotte AI into GRC use cases beyond the SOC
- Pattern: CrowdStrike has been actively acquiring to extend Falcon's surface area
  - **Adaptive Shield** (Nov 2024, ~$300M cash + stock) — SaaS security posture management
  - **Flow Security** (Mar 2024, ~$200M) — data security posture
  - **Bionic** (Oct 2023, ~$350M) — application security posture
  - **Humio** (Feb 2021, ~$400M) — log management / Falcon LogScale
- Compliance OS is the same playbook: tuck-in that extends Falcon into a budget Falcon doesn't currently address

### AuditBoard (now Hg Capital portfolio)
- Adds real-time security telemetry they cannot build fast enough internally
- Makes their platform stickier for security-heavy enterprises and regulated industries
- Hg acquired AuditBoard in **May 2024 at a reported ~$3B valuation**; PE-backed playbook is bolt-on M&A to expand the ARR base ahead of an IPO or secondary
- The AuditBoard connector strategy positions Compliance OS as a natural acquisition rather than a competitor

### ServiceNow
- Competes with AuditBoard in GRC/IRM (ServiceNow Integrated Risk Management module)
- Acquiring Compliance OS accelerates their security evidence story without internal build cycles
- ServiceNow's recent direction: AI-led acquisitions (Element AI, Moveworks talks) and platform extension — security posture data is the missing layer for their IRM offering

### Palo Alto Networks
- Active consolidator: **Talon** (Nov 2023, $625M, enterprise browser), **Dig Security** (Nov 2023, ~$400M, DSPM), **QRadar SaaS from IBM** (May 2024 announcement). Has stated platform-consolidation thesis explicitly.
- Compliance layer is the gap CrowdStrike has not filled — owning it creates competitive differentiation

### SentinelOne
- Acquired **PingSafe** (Jan 2024, ~$100M cash + stock) for cloud security posture
- Same thesis as CrowdStrike but earlier in the platform-extension curve — needs the compliance layer to compete on board-level value

### Wiz / Snyk / other DSPM platforms
- Compliance OS framework-mapping engine is the layer they would need to enter the GRC market

**Multiple credible buyers in adjacent positions = auction dynamic = better outcome at exit.**

---

## Slide 13 — Ask

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
