# 🛒 ShopFlow Ops AI
### E-Commerce Operational Intelligence & Scenario Simulation Platform

[![Live Application](https://img.shields.io/badge/Live_App-Base44-6366f1?style=for-the-badge&logo=rocket)](https://shopflow-ops-ai.base44.app)
[![Project Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)]()
[![Type](https://img.shields.io/badge/Type-Data_&_Operations_Portfolio-blue?style=for-the-badge)]()

> **ShopFlow Ops AI** is an interactive, data-driven operational intelligence platform built to tackle real-world e-commerce logistics challenges. It translates raw operational data into actionable decision-making insights through KPI monitoring, bottleneck detection, capacity forecasting, and strategy simulation.

🌐 **[Try the Live Interactive Dashboard](https://shopflow-ops-ai.base44.app)**

---

## 📸 Interface & Capabilities Overview

Below is a visual walk-through of the key modules integrated into the platform:

| Executive Overview | High-Level Operations Dashboard |
| :---: | :---: |
| ![Overview](ShopFlowassets/Overview.png) | ![Dashboard](ShopFlowassets/Dashboard.png) |

| Bottleneck Analysis | Supply Center Performance |
| :---: | :---: |
| ![Bottleneck Analysis](ShopFlowassets/Bottleneck%20Analysis.png) | ![Supply Center](ShopFlowassets/Supply%20Center.png) |

| Scenario Simulator | Data Mining & Quality Checks |
| :---: | :---: |
| ![Scenario Simulator](ShopFlowassets/Scenario%20simulator.png) | ![Data Mining](ShopFlowassets/Data%20Mining.png) |

---

## 📌 Problem Statement & Context

E-commerce networks often struggle with unseen fulfillment bottlenecks, leading to SLA breaches, worker burnout, and inflated operational costs. **ShopFlow Ops AI** was designed as a simulation and analysis framework to answer critical questions before making costly real-world operational changes:

* *Which fulfillment stage is causing network delays right now?*
* *How will adding 5 staff or opening an extra station impact our SLA next week?*
* *Is our throughput limit driven by processing delays or raw capacity constraints?*

---

## 🌟 Core Features

* **📊 Operational KPI Tracking:** Monitors capacity utilization, SLA fulfillment rates, backlog build-up, and end-to-end fulfillment cycle times.
* **🔎 Quantitative Bottleneck Detection:** Implements a weighted 4-factor formula to pinpoint exact process blockages.
* **🧪 Deterministic Scenario Simulator:** Enables operators to model resource reallocations (labor, workstations, pick teams) and preview predicted SLA and capacity impacts.
* **🏢 Multi-Center Logistics Monitoring:** Evaluates performance variances across 5 distinct fulfillment centers.
* **🧹 Built-in Data Quality Audit:** Includes automated checks for missing fields, negative durations, duplicate orders, and integrity scoring.

---

## 📐 Analytics Methodology & Formulas

### 1. Key Performance Indicators (KPIs)

* **Capacity Utilization Rate:**
  $$\text{Capacity Utilization (\%)} = \left( \frac{\text{Current Workload}}{\text{Available Capacity}} \right) \times 100$$

* **Fulfillment SLA Rate:**
  $$\text{SLA Rate (\%)} = \left( \frac{\text{Orders Delivered On Time}}{\text{Total Eligible Orders}} \right) \times 100$$

* **Capacity Risk Thresholds:**
  * 🟢 **Healthy:** $<80\%$
  * 🟡 **Watch:** $80\% - 90\%$
  * 🟠 **High Risk:** $90\% - 100\%$
  * 🔴 **Critical:** $>100\%$

---

### 2. Weighted Bottleneck Scoring Model

To isolate root causes rather than symptoms, the platform computes a normalized Bottleneck Score ($0–100$):

$$\text{Bottleneck Score} = 0.40(CU) + 0.25(QP) + 0.20(PT) + 0.15(DS)$$

* **$CU$ (Capacity Utilization - 40%):** Level of stage overload.
* **$QP$ (Queue Pressure - 25%):** Backlog ratio against stage capacity.
* **$PT$ (Processing Time Pressure - 20%):** Real duration versus standard benchmarks.
* **$DS$ (Delay Share - 15%):** Percentage contribution to total network delays.

*Score Levels: Critical ($80+$) | High Risk ($60–79$) | Watch ($40–59$) | Healthy ($<40$)*

---

### 3. Scenario Simulation & Resource Forecasting

The simulator relies on a deterministic analytical model (ensuring full auditability and reproducibility):

$$\text{Adjusted Capacity} = \text{Base Capacity} + (\text{Labor} \times 76) + (\text{Stations} \times 340) + (\text{Pick Teams} \times 460) + \text{Process Improvements}$$

**Overall Strategy Score:**
$$\text{Scenario Score} = 0.40(\Delta SLA) + 0.30(\Delta Cap) + 0.20(\Delta Backlog) - 0.10(\text{Resource Cost})$$

---

## 🎲 Dataset Architecture

* **Volume:** 50,000 order records across 5 fulfillment centers spanning a 60-day operational window.
* **Determinism:** Built using a PRNG with a fixed seed to guarantee **100% reproducible metrics** on every load.
* **Realistic Operational Dynamics:** Includes peak hour surges ($18:00 - 21:00$), weekend demand shifts, stage-specific delays, and capacity-driven SLA drops.

---

## ⚙️ Tech & Deployment Stack

* **Platform Engine:** Built & hosted via **Base44** (Web Application Engine).
* **Analytics Layer:** Deterministic mathematical models & weighted scoring algorithms.
* **Live Deployment:** [https://shopflow-ops-ai.base44.app](https://shopflow-ops-ai.base44.app)

---

> ℹ️ *Disclaimer: All data within this project is synthetically generated for demonstration and portfolio purposes.*
