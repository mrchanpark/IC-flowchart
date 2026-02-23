# IC Memo Production Workflow

### Company-Side Fundraising Memo — Blueprint v2.0

> **100+ action steps** · **7 stages** · **5 validation gates** · **18 content sections**
> Stage-agnostic framework: Series A through Pre-IPO

---

## Color System

| Color | Phase | Sections |
|:---:|---|---|
| 🟣 | **Pre-Production** | Scoping, Ownership, Page Budget |
| 🟡 | **Validation Gates** | Gates 1–5 (hard checkpoints) |
| 🔵 | **Stage 1** — The Hook | Sections 1–2 |
| 🟢 | **Stage 2** — The Opportunity | Sections 3–5 |
| 🟩 | **Stage 3** — The Proof | Sections 6–8 |
| 🟤 | **Stage 4** — The Team | Sections 9–10 |
| 🔷 | **Stage 5** — The Numbers | Sections 11–13 |
| 🟠 | **Stage 6** — The Ask | Sections 14–15 |
| 🔴 | **Stage 7** — Risk & Close | Sections 16–18 |
| ⭐ | **Executive Summary** | Written last, after all stages |
| ✅ | **Decision & Sign-Off** | Section 19 + Gate 5 |

---

## Pre-Production: Transaction Intake

```mermaid
flowchart LR
  P01(["CEO: Initiate memo production"]):::init --> P02["Define transaction type"]:::s
  P02 --> P03["Set round size & range"]:::s
  P03 --> P04["Establish valuation basis"]:::s
  P04 --> P05["Document decision required"]:::s
  P05 --> P06["Set confidentiality tier"]:::s
  P06 --> P07["Lock data cutoff date"]:::d
  P07 --> P08["Set draft & final timeline"]:::s
  classDef init fill:#7c3aed,stroke:#6d28d9,color:#fff,font-weight:700
  classDef s fill:#ede9fe,stroke:#8b5cf6,color:#1e1b4b
  classDef d fill:#c4b5fd,stroke:#7c3aed,color:#1e1b4b,font-weight:700
```

## Pre-Production: Ownership & Scoping Decisions

```mermaid
flowchart TB
  P09["Assign Memo Owner"]:::s --> P10["Assign Financial Data Owner"]:::s
  P10 --> P11["Assign Legal / Cap Table Owner"]:::s
  P11 --> P12["Assign Product / GTM Owner"]:::s
  P12 --> P13["Resolve scoping decisions with CEO"]:::s
  P13 --> P14{"Secondary liquidity?"}:::q
  P14 -- Yes --> P15["Document sellers & amount"]:::s
  P14 -- No --> P16{"Insider participation?"}:::q
  P15 --> P16
  P16 -- Yes --> P17["Document pro rata commitments"]:::s
  P16 -- No --> P18["Confirm syndicate strategy & term sheet status"]:::s
  P17 --> P18
  P18 --> P19["Finalize page budget: ~20pg core + 30–40pg appendix"]:::m
  classDef s fill:#ede9fe,stroke:#8b5cf6,color:#1e1b4b
  classDef q fill:#c4b5fd,stroke:#7c3aed,color:#1e1b4b,font-weight:700
  classDef m fill:#7c3aed,stroke:#6d28d9,color:#fff,font-weight:700
```

---

## 🚧 Gate 1: Metrics Definition Lock

> Lock all KPI definitions before drafting — the #1 cause of credibility failure.

```mermaid
flowchart LR
  A["Define ARR methodology"]:::s --> B["Define NRR calculation"]:::s
  B --> C["Define churn: logo vs. revenue, gross vs. net"]:::s
  C --> D["Define CAC scope: fully loaded vs. direct"]:::s
  D --> E{"All definitions locked?"}:::g
  E -- No --> A
  E -- Yes --> F["Financial Data Owner: SIGN-OFF ✓"]:::pass
  classDef s fill:#fef3c7,stroke:#d97706,color:#78350f
  classDef g fill:#fbbf24,stroke:#d97706,color:#78350f,font-weight:700
  classDef pass fill:#16a34a,stroke:#15803d,color:#fff,font-weight:700
```

---

## Stage 1: The Hook — Company Overview

> *Sections 1–2 · Who are you, what do you do, and how did you get here?*

```mermaid
flowchart TB
  A["Draft Company Overview: mission, founding story, milestones"]:::s --> B["Legal: Corporate structure — entity, jurisdiction, subs"]:::s
  B --> C["Legal: Cap table summary — founders / pool / investors"]:::s
  C --> D["Finance: Headcount breakdown by function"]:::s
  D --> E["Finance: Prior funding summary — round, amount, lead"]:::s
  E --> F["Compile Section 2 — Company Overview"]:::c
  classDef s fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  classDef c fill:#2563eb,stroke:#1d4ed8,color:#fff,font-weight:700
```

---

## Stage 2: The Opportunity

> *Sections 3–5 · Market sizing, problem/solution fit, and business model economics.*

```mermaid
flowchart TB
  subgraph MKT["Section 3 · Market Opportunity"]
    direction TB
    M1["TAM: top-down from industry reports"]:::s --> M2["TAM: bottom-up from customers × ACV"]:::s
    M2 --> M3["Reconcile top-down & bottom-up"]:::s
    M3 --> M4["Define SAM & SOM with penetration logic"]:::s
    M4 --> M5["Document 2–4 market tailwinds with sources"]:::s
    M5 --> M6["Address regulatory landscape"]:::s
    M6 --> M7["Compile Section 3"]:::c
  end
  subgraph PROB["Section 4 · Problem & Solution"]
    direction TB
    P1["Quantify customer pain in $ / hours / error rates"]:::s --> P2["Document current alternatives & shortcomings"]:::s
    P2 --> P3["Present core solution mechanism"]:::s
    P3 --> P4["Customer validation: NPS, quotes, case studies"]:::s
    P4 --> P5["Compile Section 4"]:::c
  end
  subgraph BIZ["Section 5 · Business Model"]
    direction TB
    B1["Revenue model: pricing tiers, billing, contracts"]:::s --> B2["Unit economics: LTV, CAC, LTV:CAC, payback"]:::s
    B2 --> B3["Gross margin profile & trend over time"]:::s
    B3 --> B4["Expansion revenue mechanics"]:::s
    B4 --> B5["Compile Section 5"]:::c
  end
  MKT --> PROB --> BIZ
  classDef s fill:#ccfbf1,stroke:#14b8a6,color:#134e4a
  classDef c fill:#0d9488,stroke:#0f766e,color:#fff,font-weight:700
```

---

## Stage 3: The Proof

> *Sections 6–8 · Traction evidence, competitive defensibility, and GTM execution.*

```mermaid
flowchart TB
  subgraph TRAC["Section 6 · Traction & Key Metrics"]
    direction TB
    T1["Pull ARR/MRR trajectory — monthly & annual"]:::s --> T2["Calculate YoY & QoQ growth rates"]:::s
    T2 --> T3["Customer count trajectory & logo churn"]:::s
    T3 --> T4["NRR & gross retention from cohort data"]:::s
    T4 --> T5["Efficiency: burn multiple, rev per employee"]:::s
    T5 --> T6["Pipeline as multiple of quota"]:::s
    T6 --> T7["Compile Section 6"]:::c
  end
  subgraph COMP["Section 7 · Competitive Landscape"]
    direction TB
    C1["Build 2×2 competitive positioning map"]:::s --> C2["Win/loss data against named competitors"]:::s
    C2 --> C3["Document moats: switching costs, IP, data network"]:::s
    C3 --> C4["Compile Section 7"]:::c
  end
  subgraph GTM["Section 8 · Go-to-Market Strategy"]
    direction TB
    G1x["Define sales motion: PLG / direct / channel / hybrid"]:::s --> G2x["Funnel conversion rates by stage"]:::s
    G2x --> G3x["Quota attainment, ramp time, sales cycle length"]:::s
    G3x --> G4x["Magic number & CAC by channel"]:::s
    G4x --> G5x["Compile Section 8"]:::c
  end
  TRAC --> COMP --> GTM
  classDef s fill:#dcfce7,stroke:#22c55e,color:#14532d
  classDef c fill:#16a34a,stroke:#15803d,color:#fff,font-weight:700
```

---

## Stage 4: The Team

> *Sections 9–10 · Leadership profiles, org capability, board & advisors.*

```mermaid
flowchart TB
  A["Draft founder & C-suite profiles with domain expertise"]:::s --> B["Org chart & headcount breakdown by department"]:::s
  B --> C["Key hires planned with this round's capital"]:::s
  C --> D["Retention metrics: voluntary turnover, avg tenure"]:::s
  D --> E["Compile Section 9 — Team & Leadership"]:::c
  E --> F["Board members with backgrounds & independence status"]:::s
  F --> G["Strategic advisors & specific value provided"]:::s
  G --> H["Existing investor follow-on commitments"]:::s
  H --> I["Compile Section 10 — Board & Advisors"]:::c
  classDef s fill:#e0e7ff,stroke:#6366f1,color:#1e1b4b
  classDef c fill:#4f46e5,stroke:#4338ca,color:#fff,font-weight:700
```

---

## 🚧 Gate 2: Financial Reconciliation

> Every number traces to the model → model traces to the GL → revenue consistent everywhere.

```mermaid
flowchart LR
  A["Map every memo figure to a named model cell"]:::s --> B["Reconcile model to GL actuals: less than 1% variance"]:::s
  B --> C["Verify internal consistency: S1 = S6 = S11 = model"]:::s
  C --> D{"All 3 reconciliation layers pass?"}:::g
  D -- No --> A
  D -- Yes --> E["Finance + Memo Owner: JOINT SIGN-OFF ✓"]:::pass
  classDef s fill:#fef3c7,stroke:#d97706,color:#78350f
  classDef g fill:#fbbf24,stroke:#d97706,color:#78350f,font-weight:700
  classDef pass fill:#16a34a,stroke:#15803d,color:#fff,font-weight:700
```

---

## Stage 5: The Numbers

> *Sections 11–13 · Historical financials, forward projections, and cash/runway.*

```mermaid
flowchart TB
  subgraph HIST["Section 11 · Historical Financials"]
    direction TB
    H1["P&L summary: 2–3 FY of revenue, COGS, OpEx, EBITDA"]:::s --> H2["Balance sheet: cash, working capital, debt"]:::s
    H2 --> H3["Cash flow summary & non-recurring items"]:::s
    H3 --> H4["Quarterly trends where contextual"]:::s
    H4 --> H5["Compile Section 11"]:::c
  end
  subgraph PROJ["Section 12 · Financial Projections"]
    direction TB
    F1["3–5 year revenue forecast with quarterly Y1 detail"]:::s --> F2["Key assumptions: customer growth, ACV, NRR, hiring"]:::s
    F2 --> F3["Scenario analysis: base, bull, bear cases"]:::s
    F3 --> F4["Revenue bridge: new logos + expansion − churn"]:::s
    F4 --> F5["Path to profitability & FCF trajectory"]:::s
    F5 --> F6["Compile Section 12"]:::c
  end
  subgraph CASH["Section 13 · Cash & Runway"]
    direction TB
    R1["Current cash position at most recent month-end"]:::s --> R2["Monthly burn rate: trailing 3-month average"]:::s
    R2 --> R3["Runway in months & post-raise runway"]:::s
    R3 --> R4["Cash waterfall: opening + raise − projected burn"]:::s
    R4 --> R5["Map milestones to capital required & timelines"]:::s
    R5 --> R6["Compile Section 13"]:::c
  end
  HIST --> PROJ --> CASH
  classDef s fill:#cffafe,stroke:#06b6d4,color:#164e63
  classDef c fill:#0891b2,stroke:#0e7490,color:#fff,font-weight:700
```

---

## 🚧 Gate 3: Cap Table & Legal Reconciliation

```mermaid
flowchart LR
  A["Verify current ownership percentages"]:::s --> B["Verify option pool size & outstanding convertibles"]:::s
  B --> C["Calculate pro forma ownership post-raise"]:::s
  C --> D["External counsel: confirm all obligations"]:::s
  D --> E{"Cap table fully reconciled?"}:::g
  E -- No --> A
  E -- Yes --> F["Legal + Counsel: JOINT SIGN-OFF ✓"]:::pass
  classDef s fill:#fef3c7,stroke:#d97706,color:#78350f
  classDef g fill:#fbbf24,stroke:#d97706,color:#78350f,font-weight:700
  classDef pass fill:#16a34a,stroke:#15803d,color:#fff,font-weight:700
```

---

## Stage 6: The Ask

> *Sections 14–15 · Define the raise, justify the valuation, make the investment case.*

```mermaid
flowchart TB
  subgraph RAISE["Section 14 · The Raise"]
    direction TB
    R1["State round size & structure"]:::s --> R2["Pre-money & post-money valuation"]:::s
    R2 --> R3["Use of proceeds: 3–5 categories with $ and %"]:::s
    R3 --> R4["Pro forma ownership table / dilution impact"]:::s
    R4 --> R5["Target close timeline & existing commitments"]:::s
    R5 --> R6{"Transaction mechanics needed?"}:::q
    R6 -- Yes --> R7["Secondary split, insider participation, syndicate strategy"]:::s
    R6 -- No --> R8["Compile Section 14"]:::c
    R7 --> R8
  end
  subgraph VAL["Section 15 · Valuation Support"]
    direction TB
    V1["Comparable company analysis: 5–8 comps with multiples"]:::s --> V2["Precedent transactions at comparable stage"]:::s
    V2 --> V3["Growth-adjusted multiples"]:::s
    V3 --> V4{"Business mature enough for DCF?"}:::q
    V4 -- Yes --> V5["Build DCF: WACC + terminal value"]:::s
    V4 -- No --> V6["Triangulate implied valuation range: low / mid / high"]:::s
    V5 --> V6
    V6 --> V7["Internal bridge-to-offer: floor / target / ceiling"]:::s
    V7 --> V8["Market condition note & comp refresh date"]:::s
    V8 --> V9["Compile Section 15"]:::c
  end
  RAISE --> VAL
  classDef s fill:#ffedd5,stroke:#f97316,color:#431407
  classDef q fill:#fdba74,stroke:#ea580c,color:#431407,font-weight:700
  classDef c fill:#ea580c,stroke:#c2410c,color:#fff,font-weight:700
```

---

## Stage 7: Risk & Close

> *Sections 16–18 · Risks & mitigants, milestones, and appendix assembly.*

```mermaid
flowchart TB
  subgraph RISK["Section 16 · Key Risks & Mitigants"]
    direction TB
    K1["Market risks: demand volatility, competitive threats, macro"]:::s --> K2["Execution risks: key person, hiring, product delivery"]:::s
    K2 --> K3["Financial risks: concentration, capital needs, dilution"]:::s
    K3 --> K4["Regulatory risks: compliance, litigation, IP, privacy"]:::s
    K4 --> K5["Pair each risk with a specific, measurable mitigant"]:::s
    K5 --> K6["Compile Section 16"]:::c
  end
  subgraph MILE["Section 17 · Milestones & Path Forward"]
    direction TB
    M1["12–18 month milestone plan with quarterly waypoints"]:::s --> M2["Identify next-round trigger metrics"]:::s
    M2 --> M3["Articulate long-term vision & potential exit paths"]:::s
    M3 --> M4["Compile Section 17"]:::c
  end
  subgraph APPX["Section 18 · Appendices Index"]
    direction TB
    A1["Build index: A-series, B-series, C-series, D-series codes"]:::s --> A2["Apply confidentiality tiering to each item"]:::s
    A2 --> A3["Compile Section 18 — Appendix Index"]:::c
  end
  RISK --> MILE --> APPX
  classDef s fill:#fee2e2,stroke:#ef4444,color:#450a0a
  classDef c fill:#dc2626,stroke:#b91c1c,color:#fff,font-weight:700
```

---

## ⭐ Executive Summary — Written Last

> *After all 17 sections are complete, write the exec summary. Max 1 page.*

```mermaid
flowchart LR
  A["Draft 1-sentence company description"]:::s --> B["Pull 3–5 finalized headline metrics: ARR, growth, NRR"]:::s
  B --> C["Summarize round size, valuation, use of proceeds"]:::s
  C --> D["Write forward-looking milestone statement"]:::s
  D --> E["Compile Section 1 — Executive Summary — max 1 page"]:::c
  classDef s fill:#fef9c3,stroke:#ca8a04,color:#713f12
  classDef c fill:#ca8a04,stroke:#a16207,color:#fff,font-weight:700
```

---

## 🚧 Gate 4: Appendix Completeness

```mermaid
flowchart LR
  A["Review each section for data-dependent claims"]:::s --> B{"Every claim has appendix support?"}:::g
  B -- No --> C["Add evidence OR remove unsupported claim"]:::fix
  C --> A
  B -- Yes --> D["Verify customer references cleared"]:::s
  D --> E["Verify product screenshots current"]:::s
  E --> F["Verify market data sources cited"]:::s
  F --> G["Memo Owner: SIGN-OFF ✓"]:::pass
  classDef s fill:#fef3c7,stroke:#d97706,color:#78350f
  classDef g fill:#fbbf24,stroke:#d97706,color:#78350f,font-weight:700
  classDef fix fill:#fed7aa,stroke:#ea580c,color:#431407
  classDef pass fill:#16a34a,stroke:#15803d,color:#fff,font-weight:700
```

---

## ✅ Decision & Approval Block — Section 19

```mermaid
flowchart LR
  A["Draft decision requested: specific approval sought"]:::s --> B["Define approval conditions & non-negotiables"]:::s
  B --> C["Define acceptable negotiation range"]:::s
  C --> D["Document fallback plan with quantified runway"]:::s
  D --> E["Define escalation triggers requiring re-approval"]:::s
  E --> F["Compile Section 19 — Decision & Approval Block"]:::c
  classDef s fill:#dcfce7,stroke:#22c55e,color:#14532d
  classDef c fill:#15803d,stroke:#166534,color:#fff,font-weight:700
```

---

## 🚧 Gate 5: Final Sign-Off & Pre-Submission QC

```mermaid
flowchart TB
  subgraph QC["Pre-Submission Checklist"]
    direction TB
    Q1["All financials match model exactly"]:::ck --> Q2["Revenue/ARR consistent across S1, S6, S11, S12, S14"]:::ck
    Q2 --> Q3["Burn rate uses trailing 3-month actuals"]:::ck
    Q3 --> Q4["Use of proceeds ties to hiring plan & milestone map"]:::ck
    Q4 --> Q5["Comp set refreshed within 30 days"]:::ck
    Q5 --> Q6["Customer names/logos NDA-cleared"]:::ck
    Q6 --> Q7["Risk disclosures reviewed by Legal"]:::ck
    Q7 --> Q8["No section exceeds page budget by more than 50%"]:::ck
    Q8 --> Q9["Appendix index complete with version numbers"]:::ck
  end
  Q9 --> PASS{"All checks pass?"}:::g
  PASS -- No --> Q1
  PASS -- Yes --> S1x["Financial Data Owner ✓"]:::sign
  S1x --> S2x["Legal / Cap Table Owner ✓"]:::sign
  S2x --> S3x["CEO ✓"]:::sign
  S3x --> S4x["Memo Owner ✓"]:::sign
  S4x --> DONE(["🚀 MEMO CLEARED FOR DISTRIBUTION"]):::go
  classDef ck fill:#e2e8f0,stroke:#475569,color:#1e293b
  classDef g fill:#fbbf24,stroke:#d97706,color:#78350f,font-weight:700
  classDef sign fill:#86efac,stroke:#16a34a,color:#14532d,font-weight:700
  classDef go fill:#16a34a,stroke:#15803d,color:#fff,font-weight:700
```

---

## Step Count

| Phase | Steps |
|---|:---:|
| Pre-Production: Scoping | 8 |
| Pre-Production: Ownership | 11 |
| Gate 1: Metrics Lock | 6 |
| Stage 1: The Hook | 6 |
| Stage 2: The Opportunity | 17 |
| Stage 3: The Proof | 16 |
| Stage 4: The Team | 9 |
| Gate 2: Financials | 5 |
| Stage 5: The Numbers | 17 |
| Gate 3: Cap Table | 6 |
| Stage 6: The Ask | 17 |
| Stage 7: Risk & Close | 13 |
| Executive Summary | 5 |
| Gate 4: Appendix | 7 |
| Decision Block | 6 |
| Gate 5: Sign-Off & QC | 15 |
| **Total** | **164** |

---

## Usage

**GitHub** — Push this `README.md` to any repo. GitHub renders Mermaid natively.

**Interactive** — Paste individual charts at [mermaid.live](https://mermaid.live)

**Export to SVG/PNG:**

```bash
npm install -g @mermaid-js/mermaid-cli
mmdc -i chart.mermaid -o chart.svg -w 2400
```

**Presentation** — Open `ic_memo_workflow_presentation.html` in any browser for a dark-mode, scroll-animated presentation with sidebar navigation.

---

*IC Production Blueprint v2.0 · Confidential*
