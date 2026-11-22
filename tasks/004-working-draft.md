# 004: Working draft

- **Status:** active
- **Created:** 2026-11-17
- **Updated:** 2026-11-21
- **Due:** 2026-11-22, 11:59 pm

## Goal

A notebook that loads `data/wqp_cahaba_phosphorus.csv` from a clean start, cleans it in code (units, results not detected, blank fraction, field replicates), explores the five ADEM stations' growing-season phosphorus, retains pre-2006 measurements as legacy data because their fraction is mostly unspecified, and compares confirmed post-2006 total-phosphorus medians with the 35 µg/L target.

## Done when

The notebook runs top to bottom after a kernel restart; `judgment-log.md` has at least two entries about these data; at least two tasks of my own have dated progress entries, with one left open for the next step; and the URL of the pushed commit is on Canvas.

## Progress log

- 2026-11-17: Closed tasks 001–003 and moved them to `tasks/archive/`. Changed the data path in `AGENTS.md` to the relative `data/wqp_cahaba_phosphorus.csv`.
- 2026-11-17: Added the Parameters section to `topic.ipynb`. Set the growing season to April 1 through October 31, inclusive.
- 2026-11-17: Began the cleaned-table work. Kept the five largest ADEM stations, converted ug/L to mg/L, filtered to growing-season total-phosphorus water results, and grouped medians before and after September 2006.
- 2026-11-17: Added an audit cell to inspect older growing-season records' fraction, units, detection flags, qualifiers, status, and detection limits before deciding how to treat them.
- 2026-11-20: Kept pre-2006 records as legacy phosphorus because 343 of 346 selected growing-season rows have no sample-fraction label. Separated their nondetection sensitivity medians from the post-2006 total-phosphorus comparison and updated the plot so the legacy and post-2006 periods are not presented as directly comparable. Ran all 12 notebook code cells top to bottom; the filtered post-2006 total-phosphorus data contained 450 detected samples and no nondetects.
- 2026-11-21: Reviewed the two high station 21AWIC-672 results against other stations sampled on the same dates. Excluding station 21AWIC-672, the other recording stations had same-day medians of 0.106 mg/L on 2015-10-07 and 0.143 mg/L on 2019-10-01, both above the 0.035 mg/L target. Kept the two flagged station results in the primary analysis; completed task 005 and left task 004 open for draft submission.
- 2026-11-21: Executed all 19 notebook code cells in order in a fresh project Python session; all completed. The only messages were expected non-interactive plotting warnings from the headless check.

## Outcome
