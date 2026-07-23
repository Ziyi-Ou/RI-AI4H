# RI ScreenConnect

**Live application:** https://ziyi-ou.github.io/RI-AI4H/

RI ScreenConnect is a static GitHub Pages product prototype for the Rhode Island AI4H Data Challenge.

It connects two practical pieces of the cancer-screening journey:

1. helping organizations understand where screening outreach may have the greatest local impact; and
2. helping patients or care teams compare convenient screening options after screening has already been recommended.

The appointment-search experience uses simulated facility availability. Mammography is included as the main example, but the interface is framed as a broader screening navigator.

## Designated Users

### Health Organizations

Health systems, public-health agencies, community organizations, cancer-prevention initiatives, and outreach teams can use the **Community Needs** dashboard to:

- compare screening-gap patterns across Rhode Island cities and ZIP Code areas;
- examine SVI and Health Equity Zone context;
- compare screening gaps with flu-shot uptake as a preventive-care touchpoint;
- identify communities where awareness, navigation, or outreach resources may have greater impact.

### Patients and Caregivers

Patients or caregivers can use **Find Screening** after a clinician has already recommended screening.

The navigator helps compare sample appointment options by screening type, ZIP code, date, time, insurance category, travel distance, language preference, accessibility needs, and referral status.

### Providers and Care Teams

Providers, care coordinators, navigators, and clinic staff can use the same **Find Screening** workflow to help a patient compare practical appointment options.

The static prototype does not send referrals, verify coverage, or complete real bookings.

## Data Boundary

This prototype uses **SyntheticRI**, which contains synthetic, not real, patient records.

The Community Needs dashboard shows population-level planning outputs and cannot identify or contact actual residents. Displayed values should not be interpreted as verified Rhode Island screening rates.

The Find Screening flow uses simulated appointment availability and does not collect personal health information. In a deployed version, final scheduling and personal information would be handled directly by the selected participating facility.

## Website Structure

- **Home:** RI ScreenConnect product landing page.
- **Community Needs:** embedded population-health cancer screening gap dashboard.
- **Find Screening:** appointment navigator using simulated facility availability.
- **Partners:** concise partner value proposition.

## Main Files

- `index.html` — product landing page, routing, and appointment navigator.
- `RI_cancer_screening_dashboard_300k.html` — self-contained SyntheticRI 300K population-health dashboard.
- `assets/ri-screenconnect-icon.png` — official product icon and favicon.
- `assets/ri-screenconnect-title.png` — RI ScreenConnect wordmark.
- `assets/icons/ri-screenconnect/` — supporting product icon set used across the interface.
- `README.md` — project documentation.

No server, database, authentication system, or live scheduling integration is required for the current static GitHub Pages prototype.
