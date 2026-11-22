# Judgment log: <Jordan South>

## How I used AI in this project

(Final submission only.)

## Entries

### Nov 17: how to handle pre-2006 data
**What the assistant suggested:** There was an issue with the pre-2006 data. Before the limit was established, most of the data has no sample-fraction label. The assistant suggests to keep the data, but mark it is "legacy data."
- **What I did:** I agreed
- **Why, from my data:** I believe that keeping the data for the analysis was vital for the project. If the data cannot be kept for comparison, then the next best thing would be keeping it as a legacy

### Nov 20: how to handle undetected data

- **What the assistant suggested:** In order to keep the data sets, the assistant suggested to replace undetected data with the detection limit rather than set it to zero in order to conserve the median sample data as accurately as possible.
- **What I did:** I changed it to do the calculations for both rather than choose one over the other. 
- **Why, from my data:** Both methods are valid, but both leave plenty of room for error. The only certainty is that teh sample contains little enough P that the sensor cannot detect it, but it is not realistic for it to be 0 ug / L. Doing both calculations would allow for flexability in the data analysis.

### Nov 21: how to handle potential outliers

- **What the assistant suggested:** Two samples taken (412	21AWIC-672	2019-10-01 and 384	21AWIC-672	2015-10-07) contain values 7-8 times the 35 ug / L limit established. After further investigating these data points, I was debating whether or not to use a Grubb's Test to eliminate the values as statistical outliers that could be omitted. The Assistant, however, disagreed.
- **What I did:** I decided to not use the Grubb's Test and to instead keep the data points.
- **Why, from my data:** There were several points, but the one that convinced me was that the Grubb's Test requires the measurements to be fully independant from each other. The data points examined are not independant of the other values, as they undergo the same calibration and instrumentation, with the only difference being the time and date that the sample was taken. Another major reason is that the Grubb's Test is meant to examine only one potentialoutlier at a time. This data set included two, making the Grubb's Test suboptimal for this scenario