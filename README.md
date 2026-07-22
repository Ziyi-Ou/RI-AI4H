# RI ScreenConnect

**Live application:** https://ziyi-ou.github.io/RI-AI4H/

RI ScreenConnect is a static GitHub Pages prototype for the Rhode Island AI4H Data Challenge. It connects two parts of the cancer-screening journey:

1. helping health organizations explore where screening outreach may be most needed; and
2. helping patients or care teams find convenient screening options after screening has already been recommended.

The appointment-search experience currently uses **mammography as the example screening type**, but the product concept is designed as a broader screening navigator.

---

## Designated Users

### Health Organizations

Intended users include health systems, public-health agencies, community organizations, cancer-prevention initiatives, and outreach teams.

These users can open the **Community Needs** dashboard to:

- compare screening-gap patterns across Rhode Island cities and ZIP Code areas;
- review city-level and ZIP-level screening-gap views;
- examine social vulnerability and Health Equity Zone context;
- compare screening gaps with flu-shot uptake as a preventive-care touchpoint;
- identify communities where awareness, navigation, or outreach resources may have greater impact.

The dashboard uses aggregated SyntheticRI outputs and is intended for planning, not patient identification.

### Patients and Caregivers

Patients or caregivers can use **Find Screening** after a clinician has already recommended screening.

The navigator helps users compare sample appointment options by:

- screening type;
- ZIP code;
- preferred date;
- preferred time;
- insurance category;
- travel distance;
- language preference;
- accessibility needs;
- referral status.

The tool does not determine whether screening is medically appropriate.

### Providers and Care Teams

Providers, care coordinators, navigators, and clinic staff can use the same **Find Screening** flow to help a patient compare options.

The workflow is designed to support a practical conversation about convenience, access needs, and next steps. It does not send referrals, verify coverage, or book appointments in the static prototype.

---

## Current Website Structure

- **Home:** RI ScreenConnect product landing page.
- **Community Needs:** embedded population-health cancer screening gap dashboard.
- **Find Screening:** screening appointment navigator with mammography as the example search.
- **Partners:** concise value proposition for health systems, screening facilities, public-health organizations, and payers.

---

## Data Boundary

This prototype uses **SyntheticRI**, which contains synthetic, not real, patient records.

The Community Needs dashboard shows population-level distributions and cannot identify or contact actual residents. Displayed values should not be interpreted as verified Rhode Island screening rates.

The Find Screening flow uses sample appointment availability. It does not collect personal health information and does not complete real booking. In a deployed version, final scheduling and personal information would be handled directly by the selected participating facility.

---

## Analytical Dashboard Views

The embedded Community Needs dashboard includes:

- **City Heatmap:** compare eligible count, gap count, and gap rate across cities.
- **Individual Distribution:** visualize sampled synthetic missed-screening records.
- **Priority Overlay:** combine screening-gap patterns with Social Vulnerability Index and Health Equity Zone context.
- **Compare With Flu Shot:** compare cancer-screening gaps with flu-shot uptake as a preventive-care touchpoint.

The dashboard currently includes colorectal, breast, cervical, and lung cancer screening analyses.

---

## Implementation

The site is implemented as static HTML, CSS, and JavaScript for GitHub Pages.

Main files:

- `index.html` — RI ScreenConnect landing page and Find Screening navigator.
- `RI_cancer_screening_dashboard_300k.html` — self-contained embedded population-health dashboard generated from the SyntheticRI 300K analysis workflow.
- `README.md` — project and user documentation.

No server, database, authentication system, or live scheduling integration is required for the current static prototype.
