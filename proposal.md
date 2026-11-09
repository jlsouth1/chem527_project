# Project proposal: phosphorus in the Cahaba River against its nutrient TMDL

Jordan South, CHEM 527, topic declaration, 2026-11-08

## Question

Question: Does the water quality in the Cahaba River exceed the median limit of 35 µg/L total phosphorus, and how has the quality changed since the limit was set in September 2006?
## Data

- **Measurements.** Water Quality Portal (National Water Quality Monitoring Council), every phosphorus result in the Cahaba River watershed, hydrologic unit 03150202, from the Alabama Department of Environmental Management (ADEM), USGS and EPA. Query: <https://www.waterqualitydata.us/data/Result/search?huc=03150202&characteristicName=Phosphorus&characteristicName=Total%20Phosphorus%2C%20mixed%20forms&mimeType=csv&zip=no>, accessed 2026-11-08, committed unchanged as `data/wqp_cahaba_phosphorus.csv` (SHA-256 `85d57afa…bfa97`).
- **Limit.** ADEM, *Final Nutrient Total Maximum Daily Loads (TMDLs) for the Cahaba River Watershed*, September 2006, <https://adem.alabama.gov/programs/water/wquality/tmdls/FinalCahabaRiverNutrientTMDLReport.pdf>: an instream total phosphorus target of 35 µg/L (0.035 mg/L), applied as the growing-season median, April to October, at three compliance points (Cahaba River at Roper Rd., at Old Montgomery Hwy, and at Shelby Co. Hwy 52). The report gives 1999–2000 growing-season medians of 560 to 1,140 µg/L at those points.

## Are the data sufficient?

**Observations.** The file holds 4,699 results from 190 sites, 1974–2026; 127 sites have fewer than 10 results. Five ADEM main-stem and tributary stations have long records on both sides of the TMDL. Counting April–October water samples, total or unlabeled fraction, without field replicates:

| Station | Before (1991–2005) | 2006 | After (2007–2025) | Median before, mg/L | Median after, mg/L |
|---|---|---|---|---|---|
| C-1 (St. Clair Co.) | 70 | 8 | 139 | 0.364 | 0.027 |
| C-2 (Shelby Co.) | 73 | 0 | 85 | 0.191 | 0.054 |
| C-3 (Shelby Co.) | 83 | 7 | 137 | 0.270 | 0.028 |
| CAHS-1 (Shelby Co.) | 23 | 8 | 133 | 0.231 | 0.032 |
| LC-1 (Little Cahaba, Jefferson Co.) | 70 | 8 | 112 | 0.080 | 0.108 |

From 2011 on, C-1 and C-3 were sampled in step, so the after period has 13 to 19 growing seasons per station, enough to compute a median for each year and a confidence bound on it.

**Variables.** Station (`MonitoringLocationIdentifier`), date (`ActivityStartDate`), value (`ResultMeasureValue`), unit (`ResultMeasure/MeasureUnitCode`), fraction (`ResultSampleFractionText`), detection condition (`ResultDetectionConditionText`), and sample type (`ActivityTypeCode`, to drop field replicates).

**What is missing or uncertain.**

- *Fraction before about 2011.* ADEM's results before about 2011 leave the fraction blank, so the before period assumes they are total phosphorus. The before medians, 0.19 to 0.36 mg/L, are the same order as the TMDL report's 1999–2000 values, which supports the assumption but does not prove it; ADEM's methods for those years would settle it.
- *Units.* The file mixes mg/L, mg/l as P, µg/L (10 results) and mg/l PO4 (9 results); these are converted in code, never in the file.
- *Results without a value.* 554 results are marked not detected and have no value; at the stations above, 4 to 22 per period. The notebook will state how they are treated and check whether the median changes.
- *Which station is which compliance point.* ADEM station codes do not name a location. Matching C-1, C-2, C-3 and CAHS-1 to Roper Rd., Old Montgomery Hwy and Shelby Co. Hwy 52 needs ADEM's station descriptions or coordinates.
- *No clean reference.* C-1, the most upstream main-stem station, had a higher median before 2006 than C-3, so it may lie below the Trussville wastewater plant and cannot serve as an unaffected control.
- *The 2006 season.* The TMDL was finalized in September 2006, partway through that growing season. Counting the 2006 season as before the limit would provide the best results, as it would give each station time to improve their systems, making the data from 2007 onwards more accuarate.
**If the data cannot answer the question.** If the data prior to 2007 is not sufficient enough to come to a strong conclusion, then I shall perform my calculations focusing only on 2007 onwards.
