# The Gift Gap: Organ Donation in Australia

FIT3179 Data Visualisation 2 — Denver Samarakoon (32911149), Monash University, October 2026.

Live page: GitHub Pages from the `main` branch (`index.html` at the repo root).

## Charts

| # | Section | File | Idiom | Data |
|---|---|---|---|---|
| 1 | Hero | `js/hero_unit_chart.vg.json` | Unit / isotype | OTA 2025 |
| 2 | Part 1 | `js/funnel_waterfall.vg.json` | Funnel bar | `data/donation_funnel.csv` (OTA 2025) |
| 3 | Part 1 | `js/donors_recipients_trend.vg.json` | Multi-line with annotations | `data/national_trend.csv` (ANZOD A1.1, A1.24) |
| 4 | Part 1 | `js/donor_pyramid.vg.json` | Population pyramid | `data/donor_age_sex.csv` (ANZOD A1.2) |
| 5 | Part 2 | `js/consent_waffle.vg.json` | Isotype / waffle | `data/consent_registration.csv` (OTA 2025) |
| 6 | Part 2 | `js/consent_slope.vg.json` | Slope graph | `data/donors_by_state_year.csv` (ANZOD Table 2.1) |
| 7 | Part 3 | `js/dpmp_choropleth.vg.json` | **Map 1:** diverging choropleth | ANZOD Table 2.1 + ABS ASGS state boundaries |
| 8 | Part 3 | `js/state_year_heatmap.vg.json` | Heatmap matrix | ANZOD Table 2.1 |
| 9 | Part 3 | `js/dpmp_hexmap.vg.json` | **Map 2:** hexagonal tile map | `data/organs_leaving_state_2025.csv` (ANZOD A1.25) |
| 10 | Part 4 | `js/donor_hospitals_map.vg.json` | **Map 3:** proportional symbol map | `data/donor_hospitals.csv` (ANZOD A1.3) |
| 11 | Part 4 | `js/organ_flows.vg.json` | **Map 4:** flow map (tapered lines) | `data/organ_flow_lines_2025.csv` (ANZOD A1.25) |
| 12 | Part 5 | `js/world_dpmp.vg.json` | **Map 5:** world choropleth | `data/world_dpmp.csv` (IRODaT 2024) |

## Data notes

- All ANZOD CSVs were extracted unchanged from the ANZOD Registry Annual Report 2026 Excel
  files (Chapter 2 and Appendix I: Australian Data Tables).
- `organs_leaving_state_2025.csv` and `organ_flows_2025.csv` sum all solid organs in Table A1.25
  (2025 rows). `organ_flow_lines_2025.csv` is the same flows in long format, with each line
  shifted 0.45° to the right of travel so that A→B and B→A don't sit on top of each other.
- `donor_hospitals.csv` keeps hospitals with 5 or more donors in 2021–2025. The author geocoded
  the hospital coordinates by hand from street addresses.
- `donor_age_sex.csv` combines 2021–2025 so the pyramid has enough donors (2,472) to show a
  stable shape.

## TODO before submission

- [x] World map data: `data/world_dpmp.csv` holds all 83 countries from IRODaT's
      *Worldwide Actual Deceased Organ Donors Rate 2024 (pmp)*. Australia and NZ use the IRODaT 2024
      values here (19.74, 13.21) so every country shares one source and year; the rest of the page
      uses ANZOD 2025 (Australia 20.2). Malta, Singapore and Hong Kong are too small for the 1:110m map.
      Add the exact IRODaT URL for this chart to the footer source list if you have it.
- [ ] Spot-check the OTA figures used in the funnel, waffle and narrative (89,000 deaths,
      1,670 eligible, 53% consent, 8 in 10 vs 4 in 10) against the 2025 factsheet.
- [ ] Spot-check hospital coordinates in `data/donor_hospitals.csv`.
- [ ] Check the AI declaration wording in the footer.

## Run locally

```
python3 -m http.server
```

then open http://localhost:8000.
