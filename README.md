# Rhode Island Cancer Screening Gap Explorer

An interactive public-health decision-support tool for identifying cancer screening gaps, understanding community vulnerability, and connecting priority areas with potential clinical and community outreach channels.

**Live application:**  
https://ziyi-ou.github.io/RI-AI4H/

---

## Overview

Routine cancer screening supports early detection and prevention, but screening opportunities may be missed unevenly across populations and geographic areas.

The Rhode Island Cancer Screening Gap Explorer uses the 300,000-patient SyntheticRI longitudinal electronic health record dataset to:

- identify patients who are eligible for recommended cancer screening;
- detect documented screening events;
- estimate screening gaps;
- compare screening needs across age groups and geographic areas;
- incorporate area-level social vulnerability;
- identify possible clinical and community pathways for targeted outreach.

The tool was developed for the **Rhode Island AI4H Data Challenge**.

---

## Public-Health Questions

The application is designed around four practical questions:

1. **Where is screening need concentrated?**
2. **How are missed-screening patients spatially distributed?**
3. **Where do elevated screening gaps and social vulnerability coincide?**
4. **Which existing clinical or community channels may help support outreach?**

---

## Application Views

### 1. City Heatmap

The city-level choropleth summarizes screening need using three complementary metrics:

- **Eligible count:** where the screening-eligible population is concentrated;
- **Gap count:** where the largest absolute number of missed screenings occurs;
- **Gap rate:** where the relative screening gap is most severe.

The city-level analysis retains broader population coverage because city information is more complete than patient ZIP Code information in SyntheticRI.

### 2. Individual Distribution

This view displays a privacy-safe sample of individual missed-screening locations.

It helps reveal spatial patterns that may be hidden by city-level summaries, including within-city clustering and geographic variation in screening need.

### 3. Priority Overlay

The ZIP Code Tabulation Area–level Priority Overlay combines:

- ZIP-level screening gap estimates; and
- the CDC/ATSDR 2022 Social Vulnerability Index.

Each ZCTA is classified into one of four descriptive outreach-priority groups:

- **High Gap + High Vulnerability**
- **High Gap + Lower Vulnerability**
- **Lower Gap + High Vulnerability**
- **Lower Gap + Lower Vulnerability**

Areas with limited screening denominators or incomplete data are classified as **Insufficient Data**.

The overlay is intended to support outreach planning. It is not a clinical risk score, causal model, or validated prioritization algorithm.

### 4. Compare With Flu Shot

This view compares local screening gaps with influenza-vaccination uptake.

Flu vaccination does not explain cancer-screening gaps, but vaccination encounters may represent existing preventive-care touchpoints where screening reminders could potentially be incorporated.

Areas with fewer preventive-care contacts may require more direct community-based outreach.

---

## Social Vulnerability Index

The application uses the **CDC/ATSDR 2022 Social Vulnerability Index**, derived from 2018–2022 American Community Survey five-year estimates.

The overall SVI percentile combines 16 variables across four themes:

1. **Socioeconomic Status**
   - poverty;
   - unemployment;
   - housing cost burden;
   - educational attainment;
   - health insurance coverage.

2. **Household Characteristics**
   - older adults;
   - children;
   - disability;
   - single-parent households;
   - English language proficiency.

3. **Racial and Ethnic Minority Status**

4. **Housing Type and Transportation**
   - multi-unit housing;
   - mobile homes;
   - crowding;
   - vehicle access;
   - group quarters.

The overall SVI percentile is used for the Priority Overlay. Theme-specific percentiles are displayed to help describe the vulnerability profile of a selected area.

SVI represents **area-level context** and should not be interpreted as an individual patient characteristic.

---

## Rhode Island Health Equity Zones

Rhode Island Health Equity Zones are displayed as an optional community-partner overlay.

HEZs represent existing local collaboratives that may provide infrastructure for community-engaged public-health outreach.

Users can:

- display HEZ boundaries or representative locations;
- view HEZ names and coverage descriptions;
- identify priority ZCTAs that overlap with an HEZ;
- explore possible community partnership pathways.

HEZ is shown as contextual implementation infrastructure and is **not included in the Priority Overlay classification**.

Because HEZs vary in geographic scale, some boundaries may be based on official administrative coverage, reconstructed from documented coverage descriptions, or represented by a point when no defensible polygon is available.

---

## Screening Definitions

Screening eligibility and documented screening events were derived from computable interpretations of U.S. Preventive Services Task Force recommendations.

The current application includes:

- colorectal cancer;
- breast cancer;
- cervical cancer;
- lung cancer.

Prostate cancer screening is not included because the balance of benefits and harms is more limited and screening generally depends on individualized shared decision-making.

Colorectal cancer is used as the primary example in the project because its SyntheticRI screening estimate provided the most credible comparison with an external national benchmark.

---

## Analytical Workflow

The application follows the workflow:

```text
SyntheticRI longitudinal EHR data
            ↓
Computable screening eligibility rules
            ↓
Documented screening-event detection
            ↓
Patient-level screening-gap classification
            ↓
City- and ZIP-level geographic summaries
            ↓
SVI and HEZ contextual integration
            ↓
Interactive outreach decision-support interface
