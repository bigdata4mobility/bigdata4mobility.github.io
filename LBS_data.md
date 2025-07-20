
[<< Back to Home Page](README.md)

# Open Source LBS Data
This page will explore some of the available open source LBS datasets.

---

## 1. GeoLife

[(GeoLife Data User Guide and Download Link)](https://www.microsoft.com/en-us/research/publication/geolife-gps-trajectory-dataset-user-guide/?msockid=0f4995297f3a650f12fc80447e91644b)

### Data Description
GeoLife data is a GPS trajectory dataset collected in (Microsoft Research Asia) GeoLife project by 182 users in a period of over three years (from April 2007 to August 2012). The majority of the data was created in Beijing, China (although this dataset is distributed in over 30 cities of China and even in some cities located in the USA and Europe). Following is the summary statistics of the metrics for GeoLife data property and more detailed study and discussion of data characteristics can be found in this **[page](datapage_geolife.md)**.

**Summary Statistics of Metrics for GeoLife Data Property**

| Property | Metrics | Mean | Std | Min | 25% | 50% | 75% | Max |
|----------|---------|------|-----|-----|-----|-----|-----|-----|
| Data Stability | Number of devices per day | 5.93 | 6.24 | 1 | 2 | 3 | 8 | 29 |
| Data Statility | Number of records per device per day | 2231.92 | 3443.03 | 1 | 457 | 1183 | 2788 | 59769 |
| Temporal Sparsity | Intra-day occupancy (number of 30-min time slots observed in a day - out of 48 time slots) | 7.60 | 6.31 | 1 | 3 | 6 | 10 | 48 |
| Temporal Sparsity | Inter-day occupancy (numbre of days observed within a time period - out of data period of 1980 days) | 174.41 | 318.56 | 1 | 11 | 71 | 167.50 | 1934 |
| Temporal Gap | Time interval between consecutive location observations for a single device (seconds) | 109.61 | 46,652.38 | 0 | 1 | 2 | 5 | 1,257,394 |
| Spatial Gap | Spatial distance between consecutive location observations for a single device (meters) | 73.24 | 11,919.00 | 0 | 2.36 | 8.73 | 17.64 | 11,129,650 |
| Precision |  Spatial uncertainty radius (meters) | n/a | n/a | n/a | n/a | n/a | n/a | n/a |
| Representation | Share of the LBS users vs. pupulation in the same area | 182 users vs. 19,612,368 population in Beijing, China (2010 6th China Census) |


[More detailed study and discussion of characteristics of GeoLife Data >>](datapage_geolife.md) 

---
## 2. Other Open Source LBS Data

Other open source LBS datasets will be added when identified and explored.


