---
title: "Inventory Demand Forecasting for Steel Service Centers"
type: use-case
status: draft
date: "2025-Q3"
domain: Other
client: "Enmark"
technologies: [XGBoost, Prophet, Envision]
experts: ["@AndriiZolotarov"]
tags: [DemandForecasting, InventoryManagement, MachineLearning, SupplyChain, SteelIndustry, PurchasingAutomation]
---

# Inventory Demand Forecasting for Steel Service Centers

> **One-liner summary** — INSART is building a machine learning–based demand forecasting engine for the Enmark platform that recommends what steel service center purchasers should buy, how much, and when.

---

## Problem Overview

Steel service centers must constantly decide what steel products to buy, how much to buy, and when to buy it. Getting this wrong is costly in both directions: overbuying ties up capital in unsellable inventory, while underbuying causes stockouts and lost customers.

Today these purchasing decisions are made manually, typically in spreadsheets, based on simple historical usage averages. This approach is error-prone, cannot detect demand shifts or seasonality, ignores operational constraints, and does not scale across a growing SKU catalog or multiple warehouses.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | Manual, spreadsheet-based forecasting | Purchasers estimate future demand using historical averages in spreadsheets, with no systematic way to account for trends or seasonality. |
| 2 | Capital risk from inventory errors | Overstocking unsellable steel ties up capital; understocking causes stockouts and customer churn. |
| 3 | No visibility into demand shifts | Existing tools can't detect changing demand patterns or seasonal effects, leading to reactive rather than proactive purchasing. |
| 4 | Lack of scalability | The manual process is difficult to apply consistently across many SKUs, warehouses, and customers. |
| 5 | Fragmented data inputs | Forecasting decisions require combining sales history, usage data, open POs, and supplier lead times — currently done ad hoc. |

---

## Proposed Solution

INSART is designing an ML-based forecasting capability that analyzes historical sales, usage, and purchase order data to project SKU-level demand over a rolling 3–6 month horizon. The model output feeds a recommendation layer that accounts for current inventory, open POs, and supplier lead times to suggest order quantities and order timing.

Forecast results, along with confidence levels and key input drivers, are delivered as a structured, non-interactive tabular report inside Envision — the MVP intentionally keeps the interface simple and advisory-only, with no automated purchasing actions.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| Purchaser | Primary user; makes inventory procurement decisions using the forecast report |
| Purchasing Manager | Reviews and oversees purchasing decisions across the team |
| Operations Director | Stakeholder monitoring operational impact of forecasting accuracy |
| Company Ownership | Stakeholder monitoring capital efficiency outcomes |

---

## Process / Solution Flow

1. **Data Aggregation** — Pull sales, usage, and PO history by SKU; normalize inventory and lead time data across sources.
2. **Model Processing** — Apply statistical/ML models (e.g., XGBoost, Prophet) to forecast SKU-level demand; layer in safety stock, reorder point, and procurement timing logic.
3. **Output Generation** — Produce SKU-level recommendations (suggested order quantity and date) along with forecast confidence and key input drivers.
4. **User Interface (MVP)** — Present results as a non-interactive tabular report in Envision, with columns for SKU, forecasted demand, current inventory, in-transit inventory, months of supply, recommended order quantity, and recommended order date.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| Forecasting Models | XGBoost, Prophet | Candidate statistical/ML models for SKU-level demand forecasting over a 3–6 month horizon |
| Reorder Logic | Static rules (ROP, EOQ, safety stock) | MVP uses static reorder logic; dynamic safety stock is a post-MVP enhancement |
| Reporting / UI | Envision | Forecast output delivered as a structured, non-interactive tabular report |
| Data Inputs | Sales transactions, usage data, purchase orders, inventory on-hand/in-transit, mill/vendor lead times | Minimum data requirements for the MVP |
| Infrastructure | _[To be added]_ | Not specified in source document |
| Integrations | _[To be added]_ | Not specified in source document |

_MVP is advisory-only by design — no automated PO submission, supplier ranking/pricing optimization, interactive UI, or dynamic safety stock logic in scope for v1._

---

## Business Outcome

_[To be added — project is at MVP/proposal stage; no delivery results yet.]_

Planned evaluation metrics once piloted:
- Forecast accuracy (MAPE or RMSE)
- Recommendation precision (alignment with actual buyer decisions)
- Reduction in stockouts or overstock incidents (pilot data)
- Report adoption and usage rate within Envision

---

## Lessons Learned

_[To be added — to be completed after MVP pilot and delivery.]_

Risks identified during planning, with mitigation strategies:
- Forecast error leading to bad purchase decisions → start advisory-only, show confidence scores
- Low user trust → provide visibility into model inputs and feature importance
- Data inconsistency across customers → pilot with one or two customers, validate schema consistency
- Model complexity hindering adoption → keep initial output simple, avoid automating decisions early

---

## Reusable Components / Patterns

- [ ] _[To be added]_

---

## Resources

| Resource | Link |
|---|---|
| Code Repository | _[To be added]_ |
| Slide Deck | _[To be added]_ |
| Design Files | _[To be added]_ |
| Demo Video | _[To be added]_ |
| Source Document | Use Case Document — Inventory Demand Forecasting for Steel Service Centers, v1.0, 23/07/2025 |

---

## Experts

| Expert | Role on Project |
|---|---|
| Andrii Zolotarov | Author / Use Case Owner |
| _[To be added]_ | _[To be added]_ |

---

_Last updated: 2026-06-22 · Status: draft_
