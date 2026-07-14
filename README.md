# ZimServicePulse: Citizen Service Hotspot & Channel Optimizer

**AI4I 2026 – Track 2: Design**  
**Team:** PulseForge Zimbabwe  
**Lead Innovator:** Dr Eng F.J Kiwa  
**Date:** 14 July 2026  
**Primary Dataset:** `01_public_service_requests.csv`

---

## Problem

Public service delivery in Zimbabwe faces persistent pressure. The official Design Track dataset (January–June 2026) shows:

- Average citizen satisfaction ≈ 3.53 / 5
- Only ≈ 73% of requests resolved on time
- Highest unresolved backlogs in Waste management, Business licensing, Social protection, Roads & transport, and Water & sanitation
- Significant variation by district, settlement type and channel (WhatsApp, Walk-in, Web portal, Call centre, Community officer)

Local authorities and national planners currently lack a single, dynamic, accessible intelligence layer that turns these records into immediate operational and policy decisions. Resource allocation (community officers, WhatsApp triage, field support) remains largely reactive.

## Solution

**ZimServicePulse** is a decision-support dashboard that:

1. Surfaces national and local KPIs (requests, backlog, satisfaction, on-time rate, Urgent flags) at a glance.
2. Enables rich exploration by province, district, settlement type, service category, primary channel and priority flag.
3. Automatically generates key insights (hotspots, channel performance differentials, equity patterns).
4. Ends with prioritised recommended actions that local authorities and ministries can act on immediately.

The experience strictly follows the Design Track 4-step storytelling flow:  
**Overview KPIs → Data Exploration → Key Insights → Recommended Actions**.

## Target Users

- District Service Manager / Local Authority Operations Lead
- Provincial / National Policy Analyst (Ministry of Local Government or Public Service)
- Digital Channels & Citizen Engagement Lead
- Community Officer / Front-line Field Worker

## Demo & Prototype

- Interactive prototype: *[Add your demo URL here]*
- High-fidelity screenshots and wireframes: `/docs` or `/screenshots`
- Live data binding: Every number and pattern is computed from the official CSV.

## How the Design Dynamically Binds to the Dataset

The prototype loads `01_public_service_requests.csv` at runtime.  
All visualisations and insights are derived live from:

`month, province, district, latitude, longitude, settlement_type, service_category, primary_channel, requests_received, requests_resolved, avg_resolution_days, pct_resolved_on_time, unresolved_backlog, citizen_satisfaction_1_5, priority_flag`

No external mock data is used.

## Architecture (High Level)

```
User (District Manager / Policy Analyst / Channels Lead / Community Officer)
          │
          ▼
┌─────────────────────────────┐
│  Progressive Web App /      │
│  Streamlit / Power BI       │  ← Responsive + WCAG 2.1 AA
│  Frontend + Filters + Map   │     Low-bandwidth / offline shell
└─────────────┬───────────────┘
              │
              ▼
┌─────────────────────────────┐
│  Data Layer                 │
│  – Official CSV load        │
│  – Aggregations & rankings  │
│  – Insight generation rules │
└─────────────┬───────────────┘
              │
              ▼
┌─────────────────────────────┐
│  Outputs                    │
│  – KPI cards & choropleth   │
│  – Channel & category views │
│  – Prioritised actions      │
│  – PDF / CSV / WhatsApp     │
└─────────────────────────────┘
```

## Accessibility (WCAG 2.1 AA)

- Contrast ≥ 4.5:1
- Touch targets ≥ 44×44 px
- Full dynamic alt-text / ARIA on every visual
- Keyboard navigation
- Responsive 320 px – 1920 px
- Low-bandwidth mode + offline PWA shell
- Language readiness (English + Shona / Ndebele)

## Setup (for local testing)

```bash
pip install streamlit pandas plotly
streamlit run app.py
```

Place the official `01_public_service_requests.csv` in the data folder.

## Known Limitations

- Dataset is synthetic aggregate sample data for design practice only — not official statistics.
- Coordinates are approximate.
- Insights and recommended actions are illustrative of decision-support capability.
- Future real-data versions require Data Protection Act compliance, institutional agreements and human oversight.

## Business Model & Deployment (Summary)

- **Model:** Institutional licensing / public-good deployment to local authorities, Ministry of Local Government and POTRAZ.
- **Deployment:** Hosted PWA + offline shell + printable reports.
- **Pilot:** 2–3 districts (urban, peri-urban, rural mix).
- **30/60/90-day plan:** Refine UX → pilot with real district users → integration recommendations for national service dashboards.

Full one-page Business Model Canvas and Deployment Plan are available as annexes in this repository.

## Team

- **Lead Innovator:** Taku Gondo
- Additional team members: *[Add names and roles]*

## Licence & Challenge Use

All design assets, code and documentation are provided for the 2026 AI for Impact Challenge evaluation and subsequent non-commercial public-sector use in Zimbabwe.

---

**PulseForge Zimbabwe | AI4I 2026 Design Track**  
*Turning public service data into action for better citizen outcomes.*
