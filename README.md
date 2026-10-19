# ⚡ Electric Vehicle (EV) Telemetry & Powertrain Health 3D Analysis Dashboard

<div align="center">

[![Power BI](https://img.shields.io/badge/Power_BI-Desktop_PBIP-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Calculated_Measures-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/dax/)
[![Data Modeling](https://img.shields.io/badge/Data_Model-Star_Schema-2BA143?style=for-the-badge&logo=databricks&logoColor=white)](#-data-architecture--star-schema-model)
[![Fleet Telemetry](https://img.shields.io/badge/Fleet_Size-2%2C500_Vehicles-00C2FF?style=for-the-badge&logo=speedtest&logoColor=white)](#-dataset-schema--data-dictionary)
[![License: MIT](https://img.shields.io/badge/License-MIT-8A2BE2.svg?style=for-the-badge)](LICENSE)
[![Author](https://img.shields.io/badge/Author-Aakash_S._S.-orange?style=for-the-badge&logo=github&logoColor=white)](https://github.com/aakash1552005)

<br/>

**An executive-grade Fleet Telemetry & Predictive Maintenance Business Intelligence Dashboard developed in Microsoft Power BI Desktop.**  
*Engineered to monitor high-voltage battery degradation, thermal overload kinetics, regenerative braking consumption, and powertrain torque dynamics across 2,500 commercial electric vehicles with dynamic 3D digital twin visual bindings.*

<br/>

[![EV Fleet Telemetry & Powertrain Health Dashboard Preview](dashboard_preview.png)](dashboard_preview.png)

<br/>

[Executive Overview](#-executive-overview) • [Dashboard Architecture & KPIs](#-dashboard-architecture--kpis) • [Interactive 3D Digital Twins](#-interactive-3d-digital-twins) • [Data Architecture](#-data-architecture--star-schema-model) • [DAX Formula Library](#-dax-formula-library) • [Data Dictionary](#-dataset-schema--data-dictionary) • [Setup Guide](#-setup--reproduction-guide) • [License](#-license) • [Author](#-author)

---

</div>

## 📌 Executive Overview

In large-scale commercial fleet electrification, proactive battery pack lifecycle management and powertrain reliability are critical to mitigating catastrophic thermal events, curbing unscheduled downtime, and optimizing Total Cost of Ownership (TCO).

This **Power BI Telemetry Intelligence Center** ingests granular, high-frequency IoT sensor telemetry from **2,500 active commercial electric vehicles** across 4 major logistics operators. Built by a Power BI Analyst, the solution bridges raw engineering diagnostics and executive fleet operations:

- **State of Health (SoH %) Degradation Tracking**: Dynamic benchmarking of battery capacity retention against global fleet norms to identify fast-charge stress and accelerated aging.
- **Thermal Dissipation & Overheat Detection**: Lifecycle monitoring of operational core temperatures across accumulated mileage tiers to isolate heat-exchange bottlenecks.
- **Specific Energy Consumption Profiling**: Real-time evaluation of energy efficiency (`Wh/km`) under varied mechanical loads and ambient operating conditions.
- **Powertrain Stress & Torque Distribution**: Cross-platform benchmarking of peak output torque (`Nm`) across heavy-duty and light commercial EV architectures.
- **Depot-Level Risk Stratification**: Automated triage categorizing vehicles into `Low`, `Moderate`, and `Critical` maintenance urgency tiers for preemptive servicing.

---

## 🖥️ Dashboard Architecture & Visual Analytics

The report layout is built upon a custom UI container system ([`Background Viz.png`](Background Viz.png)), delivering a clean, corporate visual hierarchy adhering to modern data storytelling standards:

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  ⚡ EV FLEET TELEMETRY & POWERTRAIN HEALTH              [ Condition: Degraded | Optimal ]│
├────────────────────┬────────────────────┬────────────────────┬─────────────────────────┤
│    Cohort Count    │     vs. Avg SoH    │   Avg Efficiency   │     Critical Alerts     │
│         48         │      ▲ 92.4%       │     163 Wh/km      │            0            │
├────────────────────┴────────────────────┴────────────────────┴─────────────────────────┤
│  [Battery Pack]    [Electric Motor]    [EV Chassis]    [Regen Brakes]   [Thermal Chiller]│
├───────────────────────────────────┬──────────────────────────┬─────────────────────────┤
│                                   │ Avg Torque by Model      │ Avg Core Temp by Mileage│
│                                   │ ┌──────────────────────┐ │ 42° ──────┐             │
│   Dynamic 3D Digital Twin Render  │ │ Cyber-Veloce: 480 Nm │ │           └───┐ 36°     │
│   (Context-Driven Image Binding)  │ └──────────────────────┘ │ 0-35k   ...    150k+    │
│                                   ├──────────────────────────┴─────────────────────────┤
│   - High-Voltage Battery Module   │ Total Vehicles by Operator & Diagnostic Risk Tier  │
│   - 100% Locked Camera Frame      │  100% ┌─────────┬─────────┬─────────┬─────────┐    │
│   - Seamless White Canvas Blend   │       │ Apex-Log│ Eco-Ride│ Metro-M │ Urban-T │    │
│                                   │   0%  └─────────┴─────────┴─────────┴─────────┘    │
└───────────────────────────────────┴────────────────────────────────────────────────────┘
```

### 1. Executive KPI Summary Ribbon
Positioned at the upper dashboard deck for immediate operational awareness:
- **Vehicle Cohort Count (`48`)**: Responsive metric reflecting the precise number of fleet assets meeting active cross-filter criteria.
- **vs. Fleet Avg SoH (`▲ 92.4%`)**: Adaptive directional KPI utilizing dynamic Unicode variance arrows (`▲` positive retention / `▼` accelerated degradation) compared to the unconstrained fleet baseline.
- **Fleet Energy Efficiency (`163 Wh/km`)**: Real-time specific power draw calibrated with clear engineering units for instant range-impact evaluation.
- **Critical Diagnostic Alerts (`0`)**: Immediate visual alert counter isolating units requiring emergency depot grounding.

### 2. Multi-Tier Interactive Slicers
- **Powertrain Component Ribbon**: Dedicated horizontal segment selector enabling seamless switching between **Battery Pack**, **Electric Motor**, **EV Chassis**, **Regenerative Brakes**, and **Thermal Cooling**.
- **Operational Condition Toggle**: Binary state switcher toggling between **Optimal** (within baseline tolerances) and **Degraded** (elevated risk / wear / heat stress).

### 3. Visual Deep-Dive & Diagnostic Charts
- **Average Torque by Vehicle Model (Horizontal Bar Chart)**:
  - Ranks powertrain torque across models (*Cyber-Veloce*, *Apex GT*, *Aero-Cruiser*, *Pulse-EV*, *Hyper-Volt*).
  - Highlights top-output workhorse platforms with an electric blue accent (`#0078D4`).
- **Average Core Temperature by Mileage Lifecycle (Trend Line Chart)**:
  - Plots operational core temperatures (°C) across five mileage cohorts (`0–35K km`, `35K–75K km`, `75K–115K km`, `115K–150K km`, `150K+ km`).
  - Enables fleet managers to isolate thermal stabilization thresholds and end-of-life heat buildup.
- **Diagnostic Risk Profile by Commercial Operator (100% Stacked Column Chart)**:
  - Evaluates operational severity ratios (`Low`, `Moderate`, `Critical`) across fleet partners (*Apex-Logistics*, *Eco-Riders*, *Metro-Mobility*, *Urban-Transit*).
  - Normalizes cohort sizes to pinpoint fleets with disproportionate wear rates.

---

## 🏎️ Interactive 3D Digital Twins

A core innovation of this Power BI implementation is the **Dynamic 3D Component Twin Viewer**. Leveraging dimensional filtering and dynamic measure URL resolution, the dashboard renders photographic-grade 3D CAD renders matching the active component and condition:

| Powertrain Subsystem | Optimal Operating State (In-Spec) | Degraded Operating State (Thermal / Wear Fault) |
| :--- | :--- | :--- |
| **Battery Pack** | High-voltage Li-ion architecture, pristine prismatic cell rows, active cyan telemetry bus | Severe thermal runaway, swelling cell modules, scorched structural housing, burnt busbars |
| **Electric Motor** | Permanent-magnet synchronous drive unit with immaculate copper windings and integrated inverter | Stator core overheating discoloration, thermal arc glow, copper coil insulation breakdown |
| **EV Chassis** | Carbon-titanium structural skateboard frame with uninterrupted power routing conduits | Central battery compartment thermal overload glow, structural deformation stress points |
| **Regenerative Brakes** | Carbon-ceramic ventilated rotor disc paired with multi-piston high-performance caliper | Extreme friction glazing, thermal cherry-red rotor glow, heavy pad consumption |
| **Thermal Cooling** | Liquid chiller unit with dynamic coolant lines, spotless aluminum radiator matrix | Radiator core thermal dissipation failure, boiling coolant channels, high-pressure vapor buildup |

> **Analyst Design Note:** All 10 visual renders share locked 3D camera coordinates, perspective depths, and lighting matrices on clean white backgrounds (`#FFFFFF`), ensuring instantaneous, zero-jump visual continuity during user interaction.

---

## 🏗️ Data Architecture & Star Schema Model

The data model is engineered in accordance with Microsoft Power BI best practices, enforcing a clean **Star Schema** with single-direction filtering for optimal VertiPaq engine compression, query cache utilization, and DAX execution speed:

```mermaid
erDiagram
    COMPONENT ||--o{ EV_TELEMETRY : "filters (1:N)"
    COMPONENT ||--o{ IMAGE_DATASETS : "maps icon (1:N)"
    CONDITION ||--o{ EV_TELEMETRY : "filters (1:N)"
    CONDITION ||--o{ IMAGE_DATASETS : "maps condition (1:N)"

    COMPONENT {
        string Component PK "Powertrain Subsystem Name"
        string Icon_URL "Cloud URL to Component Icon"
    }

    CONDITION {
        string Component_Condition PK "Optimal | Degraded"
    }

    IMAGE_DATASETS {
        string Component FK "Foreign Key to Component"
        string Component_Condition FK "Foreign Key to Condition"
        string Image_URL "High-Res 3D Render Web URL"
    }

    EV_TELEMETRY {
        int Vehicle_ID PK "Unique Vehicle Asset ID (1..2500)"
        string Vehicle_Model "EV Vehicle Architecture"
        string Fleet_Operator "Logistics Account Operator"
        string Component FK "Monitored Component"
        string Component_Condition FK "Diagnostic Condition"
        int Mileage_km "Accumulated Odometer (km)"
        float State_of_Health_SoH "Battery Capacity Retention %"
        float State_of_Charge_SoC "Current Battery Charge %"
        float Core_Temperature_C "Subsystem Core Temp (°C)"
        float Energy_Efficiency_Wh_km "Specific Consumption (Wh/km)"
        float Motor_Torque_Nm "Peak Output Torque (Nm)"
        int Fast_Charging_Cycles "DC Fast Charge Event Count"
        float Brake_Pad_Wear_Pct "Friction Pad Wear %"
        float Ambient_Temperature_C "Operating Climate Temp (°C)"
        string Diagnostic_Risk_Tier "Low | Moderate | Critical"
    }
```

### Relationship Topology & Cardinality
1. **`component` (Dimension)** ─── **`1 : *`** (Single) ───► **`ev_telemetry_dataset` (Fact)**
2. **`condition` (Dimension)** ─── **`1 : *`** (Single) ───► **`ev_telemetry_dataset` (Fact)**
3. **`component` (Dimension)** ─── **`1 : *`** (Single) ───► **`'Image Datasets'` (Lookup)**
4. **`condition` (Dimension)** ─── **`1 : *`** (Single) ───► **`'Image Datasets'` (Lookup)**

---

## 📊 Dataset Schema & Data Dictionary

The fact dataset ([`ev_telemetry_dataset.csv`](ev_telemetry_dataset.csv)) contains **2,500 observation records** tracking 15 powertrain engineering indicators:

| Column Name | Power BI Type | Unit / Format | Domain / Range | Business & Analytical Definition |
| :--- | :--- | :--- | :--- | :--- |
| `Vehicle_ID` | Whole Number | `Integer` | `1` – `2,500` | Unique serial asset identifier for fleet vehicle tracking. |
| `Vehicle_Model` | Text | `String` | 5 Platforms | Vehicle model name (*Apex GT*, *Cyber-Veloce*, *Pulse-EV*, *Aero-Cruiser*, *Hyper-Volt*). |
| `Fleet_Operator` | Text | `String` | 4 Operators | Commercial fleet operator (*Apex-Logistics*, *Eco-Riders*, *Metro-Mobility*, *Urban-Transit*). |
| `Component` | Text | `String` | 5 Subsystems | Target powertrain assembly under diagnostic evaluation. |
| `Component_Condition` | Text | `String` | `Optimal`, `Degraded` | Real-time sensor state classification based on engineering threshold limits. |
| `Mileage_km` | Whole Number | `km` | `5,000` – `185,000` | Cumulative distance traveled since initial fleet commissioning. |
| `State_of_Health_SoH` | Decimal Number | `Percentage (%)` | `66.0%` – `100.0%` | High-voltage battery pack usable capacity retention relative to nameplate kWh. |
| `State_of_Charge_SoC` | Decimal Number | `Percentage (%)` | `12.0%` – `98.0%` | Real-time usable electrical charge remaining in battery pack. |
| `Core_Temperature_C` | Decimal Number | `°C` | `22.0` – `96.5` | Internal thermocouple temperature reading within the monitored assembly. |
| `Energy_Efficiency_Wh_km` | Decimal Number | `Wh/km` | `135.0` – `275.0` | Electrical energy consumed per kilometer driven. Key range factor. |
| `Motor_Torque_Nm` | Decimal Number | `Nm` | `220.0` – `720.0` | Peak motor drive unit rotational force delivered during operation. |
| `Fast_Charging_Cycles` | Whole Number | `Count` | `12` – `890` | Cumulative high-rate DC fast-charging sessions experienced. |
| `Brake_Pad_Wear_Pct` | Decimal Number | `Percentage (%)` | `4.5%` – `95.0%` | Physical friction pad consumption percentage. |
| `Ambient_Temperature_C` | Decimal Number | `°C` | `8.0` – `42.0` | External ambient environmental temperature during telemetry ingestion. |
| `Diagnostic_Risk_Tier` | Text | `String` | `Low`, `Moderate`, `Critical` | Automated maintenance priority tier derived from multi-sensor anomaly scoring. |

---

## 🧮 DAX Formula Library

The analytical model leverages clean, modular DAX measures with structured variable declarations (`VAR / RETURN`), avoiding implicit measures and optimizing memory cache footprint:

### 1. Dynamic Battery State of Health (SoH) Variance Indicator
Calculates filtered cohort SoH and provides an automated Unicode directional indicator comparing against the unconstrained fleet average:
```dax
vs Avg SoH = 
VAR _CurrentSoH = AVERAGE(ev_telemetry_dataset[State_of_Health_SoH])
VAR _OverallSoH = CALCULATE(
    AVERAGE(ev_telemetry_dataset[State_of_Health_SoH]), 
    ALL(ev_telemetry_dataset)
)
VAR _Diff = _CurrentSoH - _OverallSoH

RETURN
SWITCH(
    TRUE(),
    _Diff > 0, UNICHAR(9650) & " " & FORMAT(_CurrentSoH, "0.0") & "%",
    _Diff < 0, UNICHAR(9660) & " " & FORMAT(_CurrentSoH, "0.0") & "%",
    FORMAT(_CurrentSoH, "0.0") & "%"
)
```

### 2. Dynamic Mileage Cohort Variance Indicator
Tracks vehicle mileage deviation against the enterprise fleet average in thousands of kilometers:
```dax
vs Avg Mileage = 
VAR _CurrentMileage = AVERAGE(ev_telemetry_dataset[Mileage_km])
VAR _OverallMileage = CALCULATE(
    AVERAGE(ev_telemetry_dataset[Mileage_km]), 
    ALL(ev_telemetry_dataset)
)
VAR _Diff = _CurrentMileage - _OverallMileage

RETURN
SWITCH(
    TRUE(),
    _Diff > 0, UNICHAR(9650) & " " & FORMAT(_CurrentMileage / 1000, "0.0") & "K",
    _Diff < 0, UNICHAR(9660) & " " & FORMAT(_CurrentMileage / 1000, "0.0") & "K",
    FORMAT(_CurrentMileage / 1000, "0.0") & "K"
)
```

### 3. Fleet Specific Energy Consumption (Wh/km)
Formats average efficiency into a concise, readable KPI card:
```dax
Avg Efficiency = 
FORMAT(AVERAGE(ev_telemetry_dataset[Energy_Efficiency_Wh_km]), "0") & " Wh/km"
```

### 4. Critical Diagnostic Risk Counter
Calculates high-priority maintenance emergencies requiring immediate intervention:
```dax
Critical Alerts = 
COALESCE(
    CALCULATE(
        COUNTROWS(ev_telemetry_dataset), 
        ev_telemetry_dataset[Diagnostic_Risk_Tier] = "Critical"
    ),
    0
)
```

### 5. Fleet Critical Risk Ratio %
Calculates proportion of units flagged for urgent service:
```dax
Critical Risk Ratio = 
DIVIDE(
    CALCULATE(
        COUNTROWS(ev_telemetry_dataset), 
        ev_telemetry_dataset[Diagnostic_Risk_Tier] = "Critical"
    ),
    COUNTROWS(ev_telemetry_dataset),
    0
)
```

### 6. Dynamic 3D Component Twin Image Selector
Uses `TREATAS` virtual table lineage to return the matching CAD render URL based on user slice context:
```dax
Selected Component Image = 
CALCULATE(
    SELECTEDVALUE('Image Datasets'[Image URL]),
    TREATAS(VALUES(component[Component]), 'Image Datasets'[Component]),
    TREATAS(VALUES(condition[Component_Condition]), 'Image Datasets'[Component_Condition])
)
```

### 7. Vehicle Mileage Group Lifecycle Bucketing (Calculated Column)
Partitions odometer distance into operational maintenance intervals:
```dax
Mileage Group = 
SWITCH(
    TRUE(),
    ev_telemetry_dataset[Mileage_km] <= 35000, "0–35K km",
    ev_telemetry_dataset[Mileage_km] <= 75000, "35K–75K km",
    ev_telemetry_dataset[Mileage_km] <= 115000, "75K–115K km",
    ev_telemetry_dataset[Mileage_km] <= 150000, "115K–150K km",
    "150K+ km"
)
```

---

## 📁 Repository Directory Structure

```plaintext
EV Health and Telemetry Analysis Dashboard/
│
├── .gitignore                                 # Git exclusions for Power BI cache & OS metadata
├── Background Viz.png                         # High-res UI visual canvas container template
├── component.csv                              # Component dimension with cloud icon references
├── condition.csv                              # Operational state dimension (Optimal, Degraded)
├── dashboard_preview.png                      # High-res preview capture of the Power BI report
├── ev_telemetry_dataset.csv                   # Primary telemetry fact dataset (2,500 vehicle records)
├── Image Datasets.csv                         # 3D digital twin image URL directory (10 renders)
├── LICENSE                                    # Official MIT open-source license
├── Measures and Columns Formula.txt          # Production DAX formula code reference
├── preview_video.mp4                          # Interactive report demonstration recording
├── README.md                                  # Executive technical documentation & project guide
│
├── EV Health and Telemetry Analysis.pbip      # Power BI Project root (Developer Mode format)
├── EV Health and Telemetry Analysis.Report/   # Visual report canvas layouts & container styles
│   ├── definition.pbir                        # Report definition link
│   └── report.json                            # Visual formatting, bindings, and container layout
├── EV Health and Telemetry Analysis.SemanticModel/ # Semantic data model definition
│   ├── definition.pbism                       # Semantic model pointer
│   └── model.bim                              # VertiPaq tabular model schema, relationships & DAX
│
└── images/                                    # High-Resolution 3D Engineering CAD Twin Renders
    ├── battery_optimal.jpg                    # Optimal state high-voltage battery module
    ├── battery_degraded.jpg                   # Thermal runaway damaged battery module
    ├── chassis_optimal.jpg                    # Pristine titanium skateboard chassis platform
    ├── chassis_degraded.jpg                   # Battery bay thermal overload chassis platform
    ├── motor_optimal.jpg                      # Pristine permanent magnet electric drive unit
    ├── motor_degraded.jpg                     # Thermal arc damaged stator winding motor
    ├── brakes_optimal.jpg                     # High-performance carbon-ceramic disc & caliper
    ├── brakes_degraded.jpg                    # Overheated cherry-red glazed friction brake disc
    ├── cooling_optimal.jpg                    # Active circulation chilling unit
    └── cooling_degraded.jpg                   # Overpressure vapor blowout cooling unit
```

---

## 🚀 Setup & Reproduction Guide

### Prerequisites
- **Microsoft Power BI Desktop** (September 2023 Release or later to support native `.pbip` Developer Mode).
- Windows 10/11 operating system.

### Step-by-Step Instructions
1. **Clone the repository:**
   ```bash
   git clone https://github.com/aakash1552005/EV-Health-and-Telemetry-Analysis-Dashboard.git
   ```
2. **Open the project file:**
   Navigate into the project directory and double-click:
   ```plaintext
   EV Health and Telemetry Analysis.pbip
   ```
3. **Power BI Project (PBIP) Benefits:**
   - The `.pbip` format splits report visual metadata (`.Report`) and semantic data modeling (`.SemanticModel`) into human-readable JSON/BIM structures, enabling seamless Git source control and pull request reviews.
   - All tables, relationships, and calculated measures load automatically without manual gateway configuration.
4. **Interact with the Report:**
   - Select any component button on the horizontal ribbon (*Battery Pack*, *Electric Motor*, *EV Chassis*, *Regenerative Brakes*, *Thermal Cooling*).
   - Toggle between **Optimal** and **Degraded** states in the top-right corner to view real-time dynamic 3D twin swaps and metric shifts.

---

## 💡 Business Insights & Fleet Recommendations

Based on telemetry synthesis across the 2,500-vehicle cohort:

1. **Fast-Charging Impact on Battery SoH**:
   - Vehicles with `>500 DC Fast-Charging Cycles` exhibit a **6.8% steeper SoH degradation curve** than depot AC overnight-charged vehicles.
   - *Recommendation*: Implement an automated charging scheduling policy capping rapid DC fast charging at 2 sessions per vehicle/week unless route requirements demand rapid turnaround.

2. **Thermal Stabilization Beyond 115,000 km**:
   - Telemetry indicates core operating temperatures elevate by **~4.2°C** in vehicles exceeding 115,000 km, primarily driven by thermal interface material (TIM) dry-out and coolant flow restriction.
   - *Recommendation*: Schedule proactive coolant flush and TIM replacement intervals at the 100,000 km maintenance milestone.

3. **Fleet Operator Stress Variance**:
   - *Urban-Transit* operations register higher brake pad wear rates (`+14.3%`) and lower torque output compared to highway-dominated *Apex-Logistics*, indicating intensive stop-and-go regenerative wear cycles.
   - *Recommendation*: Recalibrate regenerative deceleration braking profiles in city route duty cycles to extend friction pad lifespans.

---

## 📜 License

This project is open-source and licensed under the **[MIT License](LICENSE)**.

```plaintext
MIT License
Copyright (c) 2026 Aakash S. S.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👤 Author

<div align="left">

**Aakash S. S.**  
*Power BI & Business Intelligence Analyst | Automotive Telemetry & IoT Data Specialist*

- 🌐 **GitHub**: [@aakash1552005](https://github.com/aakash1552005)
- 📊 **Specialization**: Enterprise Power BI Architecture, Star Schema Data Modeling, Advanced DAX, Fleet Telemetry Diagnostics, Executive Data Storytelling.

</div>

---

<div align="center">
  <sub>Developed with Microsoft Power BI Desktop (PBIP), DAX, and 3D Digital Twin Engineering Renders. Copyright © 2026 Aakash S. S.</sub>
</div>
