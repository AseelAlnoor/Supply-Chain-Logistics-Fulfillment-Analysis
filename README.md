# Supply Chain Logistics & Fulfillment Performance Analysis

## Executive Overview

This data analytics project provides an end-to-end evaluation of global supply chain logistics, fulfillment efficiency, and delivery delay mechanics using the DataCo Global Supply Chain dataset. The primary objective is to diagnose the structural drivers behind late deliveries, distinguish between system configuration errors and physical operational bottlenecks, and formulate targeted, data-driven optimization strategies.

---

## Business Problem Statement

High delivery latency and elevated late delivery rates directly impair customer satisfaction, inflate operational overhead, and create logistics friction. Initial baseline metrics indicate an artificial late delivery rate exceeding **55.9%**. However, identifying actionable solutions requires isolating whether these delays stem from internal warehouse staging bottlenecks, administrative holds, carrier performance failures, or misconfigured system parameters (SLA targets).

---

## Project Objectives & Methodology

The analysis follows a structured 7-step data science methodology:

1. **Data Ingestion, Cleaning & Integrity Audits**: Inspect data schema, resolve missing values, convert temporal features, and validate numerical distribution integrity.
2. **Exploratory Data Analysis (EDA) & Baseline Diagnostics**: Establish baseline delivery status metrics, shipping mode distributions, and regional performance baselines.
3. **System SLA & Configuration Audit**: Evaluate scheduled vs. actual shipping duration variables (`Days for shipping (real)` vs. `Days for shipment (scheduled)`) to uncover structural misconfigurations.
4. **Scenario Simulation & System Recalibration**: Simulate realistic SLA adjustments for First Class and Second Class shipping modes to eliminate artificial delay metrics and quantify actual operational failure rates.
5. **Geographic & Carrier Performance Mapping**: Analyze delivery latency across international destination markets, shipping channels, and regional supply hubs.
6. **Root Cause Operational Analysis**: Segment unresolved delays into **Pre-Shipping Administrative Holds** (`PROCESSING`, `PENDING_PAYMENT`, `ON_HOLD`, `SUSPECTED_FRAUD`) vs. **In-Transit Carrier Delays** to isolate internal fulfillment friction from external logistics constraints.
7. **Strategic Recommendations & Action Plan**: Synthesize empirical findings into actionable recommendations for system SLA automated logic, warehouse picking priority queues, and logistics carrier contract renegotiation.

---

## Key Findings

| Metric / Scenario | Value / Impact | Analytical Assessment |
| --- | --- | --- |
| **Baseline Delay Rate** | 55.95% | Initial high failure rate driven heavily by hardcoded 0-day shipping SLAs. |
| **Post-SLA Simulation Delay Rate** | 42.24% | Actual operational delay rate after correcting system configuration errors. |
| **Pre-Shipping Delays Share** | 44.27% (3,023 orders) | Internal administrative holds, payment processing queues, and fraud reviews. |
| **In-Transit Delays Share** | 55.73% (3,806 orders) | External carrier transport bottlenecks across regional distribution networks. |

* **System-Level Misconfiguration**: **98.8%** of initial delays in First Class and Second Class shipping modes were caused by flawed scheduled transit windows (0 days) rather than logistics carrier failures.
* **Internal Bottlenecks**: Over **44%** of remaining delays occur before parcels are handed to carriers, representing actionable internal process improvements within company control.

---

## Strategic Action Plan

* **Automate Shipping SLA Logic**: Update ERP/WMS parameters to assign realistic scheduled transit windows for First Class (min 1-2 days) and Second Class (min 3 days) to eliminate artificial delay metrics.
* **Streamline Warehouse Clearances**: Implement automated payment validation and fraud screening to clear `PENDING_PAYMENT` and `SUSPECTED_FRAUD` queues immediately.
* **Carrier SLA Enforcement**: Renegotiate performance terms with logistics providers operating in high-latency international routes (e.g., Costa Rica, Luxembourg).

---

## Tech Stack & Tools

* **Language**: Python 3.x
* **Libraries**: Pandas, NumPy, Matplotlib, Seaborn
* **Environment**: Google Colab
