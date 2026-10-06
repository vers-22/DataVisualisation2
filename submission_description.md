# FIT3179 Data Visualisation 2 — Submission description (draft)

**The Gift Gap: Organ Donation in Australia**
Denver Samarakoon (32911149)

> Draft for the Moodle form. Edit into your own words before submitting — the interview will
> test whether you can explain these choices.

## Domain, why and who

**Domain:** health — deceased organ donation and transplantation in Australia.

**Why:** About 2,000 Australians are waiting for a transplant, but Australia's donation rate
(20.2 donors per million people in 2025) is below the national target of 25 and far behind
world leaders such as Spain. Most Australians say they support donation, yet only about a third
have registered, and only 53% of families agree when asked in hospital. The visualisation
explains why donation is so rare, shows that the family conversation is the main bottleneck,
and ends with a simple action: register and tell your family.

**Who:** the average Australian adult with no medical or statistical background. Technical terms
(such as "donors per million") are explained in plain language where they first appear.

## What: the data

| Source | Author / publisher | Used for |
|---|---|---|
| ANZOD Registry Annual Report 2026, Chapter 2 and Appendix I (Excel tables) | Australia and New Zealand Organ Donation Registry (ANZORRG), 2026 | Donors and donors per million by state 2006–2025 (Table 2.1); donors 1989–2025 (A1.1); organs transplanted (A1.24); donors by age and sex (A1.2); donors by hospital (A1.3); organs moved between states (A1.25) |
| 2025 donation and transplantation data | Organ and Tissue Authority (DonateLife), 2026 | Hospital deaths, eligible donors, families asked and consenting, consent rates, registration figures |
| Worldwide Actual Deceased Organ Donors Rate 2024 (pmp) | International Registry in Organ Donation and Transplantation (IRODaT) | Donors per million for 83 countries |
| ASGS Edition 3 state boundaries | Australian Bureau of Statistics | Australian maps (simplified in mapshaper, exported as TopoJSON) |
| world-atlas 1:110m | Mike Bostock / Natural Earth | World map boundaries |

ANZOD is the official national registry and the most recent release (data to December 2025).
Tables were copied from the Excel files into small CSVs without changing any values. Hospital
coordinates were looked up by the author. The world map uses IRODaT's 2024 figures for every
country (including Australia, 19.7) so that all countries come from one source and year; the rest
of the page uses ANZOD's 2025 figure (20.2). Total data downloaded is about 620 KB.

## How: idioms and rationale

1. **Unit chart (hero):** one dot per donor and per recipient makes the scale personal and shows
   that one donor helps several people.
2. **Nested proportional squares:** area shows the drop from 89,000 hospital deaths to 557
   donors. A bar chart cannot show both ends on one scale; nested areas keep the shocking
   ratio visible while the small stages remain readable.
3. **Annotated line chart:** donors and organs transplanted since 1989, with the 2009 reform and
   COVID-19 marked, to show change over time.
4. **Population pyramid:** donors by age and sex, so readers see that donors are mostly
   middle-aged and more often men.
5. **Isotype (person icons):** "out of 10 families" compares consent for registered and
   unregistered donors in a way that needs no axis reading.
6. **Diverging choropleth map:** state donation rates coloured above or below the target of 25,
   so the one state that meets it (Tasmania) stands out. Conic equal-area projection suited to
   Australia.
7. **Slope graph:** each state's 2018 rate against 2025, so the direction of change is the main
   visual signal.
8. **Heatmap:** state × year rates over 20 years in one compact grid; colour reveals the long-run
   increase and the pandemic dip.
9. **Hexagonal tile map (linked):** equal-sized tiles so small states are not lost; colour shows the
   share of each state's organs sent interstate.
10. **Flow map (linked):** tapered lines (thick at the donor state, thin at the transplanting state)
    show direction and volume of organs crossing state lines. Clicking a hexagon filters the flow
    map to that state's organs.
11. **Proportional symbol map:** circles sized by donors at each hospital show that a small number
    of large hospitals provide half of all donors.
12. **World choropleth:** Equal Earth projection; compares Australia with 82 other countries.

**Special features:** a click-to-filter link between the tile map and the flow map; a hand-built
line-width legend for the flow map; direct labels and annotations on charts instead of legends
where possible; hover tooltips throughout; one accent colour (coral) reserved for donors and the
key message; Fraunces and Inter typefaces; charts scale down on smaller screens.

## Use of generative AI

Claude (Anthropic) was used to help plan the page structure, extract tables from the ANZOD Excel
files into CSV, draft Vega-Lite specifications, CSS and narrative text, and review the
visualisation against the brief. All data values come from the cited sources, and all charts and
text were checked and edited by the author.
