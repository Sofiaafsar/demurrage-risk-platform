# 🚢 Demurrage Risk Prediction Platform

> A predictive analytics platform that shifts demurrage and detention management from **reactive firefighting** to **proactive prevention** — combining machine learning, real-time dashboards, and root-cause diagnostics for customs, supply chain, and product teams.

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![Sprint](https://img.shields.io/badge/sprint-1%20of%205-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Cost](https://img.shields.io/badge/infra%20cost-%E2%82%B90-brightgreen)

---

## 📌 Problem Statement

### The Hidden Cost Eating Global Supply Chains

In container shipping, **demurrage** and **detention** charges are levied when containers exceed their allotted "free time" at terminals or depots. These daily fees range from **$75 to $300 per container per day** and escalate the longer a container remains stationary. For mid-to-large importers, this can translate into **hundreds of thousands of dollars annually** — one documented case crossed **$450,000 in a single year**.

Yet, despite the financial weight, demurrage continues to be treated as an unavoidable cost of doing business. The reality is that **most of it is preventable.**

### Why It Keeps Happening

The root causes fall into four broad buckets:

- **Operational inefficiencies** — poor coordination between Sales, Purchasing, and Warehouse teams
- **External constraints** — port congestion, customs inspections, labor strikes, ULCV (Ultra-Large Container Vessel) bottlenecks
- **System fragmentation** — data siloed across SAP, ERPs, carrier portals, and email threads
- **Reactive decision-making** — teams discover problems *after* fees start accruing, with no predictive signal

### How the Industry Currently Handles It

Most logistics operations still depend on **manual, fragmented, and reactive processes**:

- **Manual tracking** via Excel spreadsheets and carrier-website lookups
- **Fragmented systems** — SAP, legacy ERPs, and forwarder tools that don't talk to each other in real time
- **Email-driven coordination** between forwarders, customs brokers, and internal teams
- **Reactive intervention** — analysts scramble *after* free time has expired
- **Heavy administrative load** — invoice validation, dispute resolution, and interface troubleshooting consume hours each week

### Real-World Failure Modes (from SME Interview)

To ground this project in operational reality, a primary interview was conducted with a supply chain analyst working on inbound logistics. The conversation surfaced **8 concrete, recurring failure modes** that drive avoidable demurrage:

| # | Root Cause | What Goes Wrong |
|---|-----------|-----------------|
| 1 | **IBD–Forwarder Misalignment** | Internal Inbound Delivery (IBD) records don't match the forwarder's data, blocking clearance |
| 2 | **Address Errors & Invoice Re-creation** | Wrong consignee details trigger invoice rework, holding the container at port |
| 3 | **Unmonitored Free-Day Buffer** | Teams lose visibility on remaining free days, missing the intervention window |
| 4 | **Email Coordination Lags** | Critical mails between forwarder, customs, and internal teams go unattended |
| 5 | **SAP Duty Report Errors** | Incorrect duty calculations delay customs clearance |
| 6 | **Delayed Internal IBD Creation** | Internal IBD bottlenecks stall downstream clearance steps |
| 7 | **Procedural Rigidity** | Teams wait for IBDs even in markets where customs doesn't require them |
| 8 | **Invoice ↔ WIPS Price Variance** | Mismatch between supplier invoice and internal procurement records triggers customs disputes |

### The Core Problem

> **Demurrage is treated as an unavoidable operating cost, when in reality 60–70% of it is preventable through earlier detection of upstream failures. Organizations lack a unified, predictive view across their inbound shipment pipeline — and the teams closest to the problem are stuck in reactive mode.**

---

## 💡 Proposed Solution

A **cloud-hosted, end-to-end demurrage intelligence platform** that integrates **predictive machine learning** with **interactive Power BI dashboards** to deliver early warnings, root-cause diagnostics, and quantified ROI to the teams who can act on them.

### What This Platform Does

#### 1. Centralized Visibility (Real-Time Dashboards)
- A **single source of truth** for shipment milestones — replacing scattered Excel sheets and carrier portals
- **Pattern recognition** — surfaces which forwarders, ports, and routes consistently drive the highest fees
- **Automated alerts** flagging containers **24–72 hours before free time expires**
- **Resource utilization views** — port, warehouse, and team capacity at a glance

#### 2. Predictive Intelligence (Machine Learning Layer)
- **Layer 1 — Risk Prediction:** XGBoost classifier predicting demurrage probability per shipment (0–100%)
- **Layer 2 — Root Cause Diagnosis:** SHAP-based explainability identifying the **top 3 risk drivers** for every flagged shipment, mapped to the 8 real-world failure modes
- **What-if simulation** — test the cost impact of alternate routing, port selection, or intervention timing
- Weekly model retraining via GitHub Actions

#### 3. Quantified Business Impact
- ₹ savings model per prevented case, broken down by root cause
- Defensible ROI projection — aligned with industry benchmarks of **10–15% logistics cost reduction** post digitization
- Audit-ready timestamps that support **demurrage invoice disputes and recovery**

## 👥 Target Users & Value Delivered

This platform is designed for **four distinct user groups**, each with a tailored view and decision context:

| User Group | Primary Use Case | Value Delivered |
|------------|------------------|-----------------|
| 🛃 **Customs Team** | Detect shipments at risk of customs-driven delays — duty errors, price variance, IBD issues | Faster clearance, fewer disputes, lower hold time |
| 🚛 **Supply Chain Operations** | Monitor live shipment risk, coordinate with forwarders, track free-day buffers | Proactive intervention before the demurrage clock starts |
| 📊 **Product Managers (Business)** | Strategic insights on root-cause trends, forwarder performance, process bottlenecks | Data-driven process redesign and vendor accountability |
| 🧠 **Technical Product Managers** | Own the platform roadmap, prioritize features, manage data and ML lifecycle, align engineering with business outcomes | Translate operational pain into shippable product increments and measurable ROI |

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Database | Supabase (PostgreSQL) | Cloud-hosted shipment data |
| ETL / Scheduling | Python + GitHub Actions | Data generation + pipeline orchestration |
| Machine Learning | Python, scikit-learn, XGBoost, SHAP | Risk prediction + explainability |
| Visualization | Power BI Desktop + Power BI Service | Descriptive + predictive dashboards |
| Project Management | Jira (free tier) | Agile sprint tracking, burndown, velocity |
| Version Control | GitHub | Code, documentation, CI/CD |
| Diagrams | draw.io | Architecture and ER diagrams |

---

## 🏃 Agile Delivery Approach

Executed in **5 two-week sprints** using Scrum methodology, with a Jira board, daily standup journal, sprint reviews, and retrospectives:

| Sprint | Theme | Status |
|--------|-------|--------|
| **Sprint 1** | Discovery, Functional Spec, Architecture | 🏃 In Progress |
| **Sprint 2** | Database design, synthetic data, Descriptive Dashboard | ⏳ Planned |
| **Sprint 3** | ML model + SHAP explainability | ⏳ Planned |
| **Sprint 4** | Predictive dashboard + cloud pipeline | ⏳ Planned |
| **Sprint 5** | Business case, documentation, demo | ⏳ Planned |

