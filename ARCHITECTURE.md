# Compliance OS — Technical Architecture

## Stack

```
Frontend:    Next.js 14 (App Router) + TypeScript
UI:          Tailwind CSS + shadcn/ui
Database:    PostgreSQL + Prisma ORM
AI:          Anthropic Claude API (claude-opus-4-7)
Auth:        NextAuth.js
Jobs:        node-cron
```

## Project Structure

```
compliance-os/
├── src/
│   ├── app/
│   │   ├── (dashboard)/
│   │   │   ├── page.tsx                # Posture overview
│   │   │   ├── controls/page.tsx       # Controls list
│   │   │   ├── controls/[id]/page.tsx  # Control detail + evidence
│   │   │   ├── risks/page.tsx          # Risk register
│   │   │   ├── findings/page.tsx       # Open findings
│   │   │   └── integrations/page.tsx  # Connector management
│   │   └── api/
│   │       ├── controls/route.ts
│   │       ├── evidence/route.ts
│   │       ├── risks/route.ts
│   │       ├── findings/route.ts
│   │       ├── sync/crowdstrike/route.ts
│   │       ├── sync/auditboard/route.ts
│   │       └── integrations/route.ts
│   ├── lib/
│   │   ├── connectors/
│   │   │   ├── base.ts                 # Connector interfaces
│   │   │   ├── crowdstrike.ts          # CrowdStrike API client
│   │   │   └── auditboard.ts           # AuditBoard API client
│   │   ├── collectors/
│   │   │   ├── agentCoverage.ts
│   │   │   ├── vulnerabilities.ts
│   │   │   └── detections.ts
│   │   ├── ai/
│   │   │   └── evidenceInterpreter.ts  # Claude interpretation layer
│   │   ├── mappings/
│   │   │   └── controlMappings.ts      # Data type → control mapping
│   │   ├── sync/
│   │   │   └── syncEngine.ts           # Main sync orchestrator
│   │   └── db.ts                       # Prisma client singleton
│   └── components/
│       ├── ComplianceScore.tsx
│       ├── ControlsTable.tsx
│       ├── EvidenceCard.tsx
│       ├── RiskHeatmap.tsx
│       ├── FindingsList.tsx
│       └── ConnectorCard.tsx
├── prisma/
│   ├── schema.prisma
│   └── seed.ts
├── .env.example
├── package.json
└── tsconfig.json
```

## Data Flow

```
CrowdStrike Falcon API
        │
        ▼
  Connector Layer
  (auth, retry, pagination)
        │
        ▼
  Collector Layer
  (agentCoverage, vulnerabilities, detections)
        │
        ▼
  Normalizer → SecurityEvent[]
        │
        ▼
  AI Layer (Claude)
  (maps to compliance language per framework)
        │
        ▼
  Control Mapping Engine
  (routes evidence to correct controls)
        │
        ├──► PostgreSQL (evidence, tests, findings, risks)
        │
        └──► AuditBoard Connector (optional)
```

## Setup

```bash
git clone https://github.com/Rumpers/compliance-os
cd compliance-os
npm install
cp .env.example .env
# Fill in .env values
npx prisma migrate dev
npx prisma db seed
npm run dev
```

## Environment Variables

```env
DATABASE_URL=postgresql://...
NEXTAUTH_SECRET=...
ANTHROPIC_API_KEY=sk-ant-...

# Set via Integrations UI (stored encrypted in DB)
# CROWDSTRIKE_CLIENT_ID=
# CROWDSTRIKE_CLIENT_SECRET=
# AUDITBOARD_BASE_URL=
# AUDITBOARD_API_KEY=
```

## Build Order

1. Prisma schema + migration
2. CrowdStrike connector + agent coverage
3. AI interpretation layer
4. Control mapping engine
5. Sync engine
6. Database writes (evidence, tests, findings)
7. Dashboard UI
8. Controls + evidence UI
9. Risk register UI
10. AuditBoard connector (optional)
11. Integration management UI
