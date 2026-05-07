# BH Anti-Poaching Report

**Bahari Hai Anti-Poaching / Marine Patrol Dashboard & Report**

Repository: `wildlife-dynamics/bh_antipoaching`

---

## Overview

This workflow processes patrol data from Bahari Hai (coastal/marine conservation area) to generate a comprehensive **anti-poaching and marine patrol report** and an interactive dashboard.

It analyses:
- Patrol effort (by transport type: Boat, Foot, Vehicle)
- Illegal activities (Mangrove Logging, Poaching, Illegal Fishing, Damaging Coral, Arrests)
- Village-level and Sector-level summaries
- Hotspot maps for illegal events and patrol effort
- Evidence breakdowns
- Temporal trends (Year / Quarter / Month)

**Outputs** include:
- Multiple HTML + PNG charts and tables
- Several geospatial hotspot and effort maps
- A professionally formatted Word report (`patrol_report.docx`)

---

## Features

- **Patrol Summaries**: Patrol counts, hours, and incidents over time
- **Effort Analysis**: Patrol hours by transport type (Boat/Foot/Vehicle)
- **Illegal Activity Dashboards**: Summary charts, donut charts, and stacked bars
- **Evidence Breakdowns**: Detailed counts for mangrove logging, poaching, and illegal fishing gear
- **Village & Sector Insights**: Proportional effort, arrests, top villages
- **Interactive Maps**: Illegal events hotspots, weighted patrol effort, standardised rate, ecograph, specific activity maps (mangrove, poaching, illegal fishing, arrests, poached turtles)
- **Automated Word Report**: All visuals assembled into one document

---

## Prerequisites

- Access to the Ecoscope Workflows platform (or compatible runner)
- Patrol data in CSV format (with columns such as `Patrol Start Date`, `Waypoint Date`, `X`, `Y`, `Patrol ID`, `Observation Category 0`, `Evidence`, `Village`, `Station`, etc.)
- Marine boundary layers (GeoPackage / shapefiles)

---

## Step-by-Step Configuration

### Step 1 — Add the Workflow Template

In the workflow runner interface:

1. Go to **Workflow Templates** → **Add Workflow Template**
2. Paste the repository URL: `https://github.com/wildlife-dynamics/bh_antipoaching.git`

3. Click **Add Template**

### Step 2 — Select and Configure the Workflow

1. Find **bh_antipoaching** in the template list and open it.
2. Fill in the configuration form:

#### Workflow Details
- **Workflow Name**: e.g., `Bahari Hai Anti-Poaching - April 2026`
- **Description**: Optional notes

#### Time Range
- **Timezone**: Usually `Africa/Nairobi` (UTC+3)
- **Since / Until**: Define the reporting period

#### Input Files (automatically fetched)
- Patrol CSV (pre-configured URL in the workflow)
- Marine layers (pre-configured)
- Report template (pre-configured)

### Step 3 — Submit & Run

Click **Submit**. The workflow will:
- Fetch patrol data
- Fetch the report template
- Fetch marine layers shapefiles to be used for mapping
- Clean and prepare the patrol data
- Generate all charts, tables, and maps
- Render the final Word report
- Save everything to `${ECOSCOPE_WORKFLOWS_RESULTS}`

---

## Output Files

All outputs are saved in the results directory.

### Summary Tables & Charts
- `patrol_summary.png` / HTML – Patrols, hours, incidents by year
- `patrols_per_year.png`, `patrol_hours_per_year.png`, `incidents_per_year.png`
- Village Patrol Summary table
- Patrol Effort by Transport Type (stacked bar)
- Patrol Count & Hours by Transport Type

### Illegal Activity Outputs
- Illegal Activity Summary dashboard
- Illegal Activities Donut chart
- Evidence breakdowns (Mangrove Logging, Poaching, Illegal Fishing Gear)
- Illegal Events by Sector (stacked)
- Arrests by Village
- Top 5 Villages charts (by category + monthly trend)

### Maps (HTML + PNG)
- **Illegal Events Map**
- **Weighted Patrol Effort Map**
- **Standardised Event Rate Map**
- **Ecograph Patrol Effort Map**
- Specific hotspot maps: Mangrove Logging, Poaching, Illegal Fishing, Arrests, Poached Turtles

### Final Report
- `patrol_report.docx` – Complete formatted report with all visuals

---


