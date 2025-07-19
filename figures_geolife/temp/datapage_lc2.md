# Open Source Dataset: GeoLife

## Data Files and Variables

### **GeoLife trajectory file**

| # | Column name   | Type   | Unit / format                | Description |
|---|---------------|--------|------------------------------|-------------|
| 1 | `lat`         | Float  | Decimal  (WGS-84)           | Latitude |
| 2 | `lon`         | Float  | Decimal (WGS-84)           | Longitude |
| 3 | `dummy`       | Int    | — (always 0)                 | Reserved placeholder |
| 4 | `altitude_ft` | Float  | Feet (–777 = missing)        | Altitude above sea level |
| 5 | `serial_days` | Float  | Days since 1899-12-30        | Excel-style numeric datetime |
| 6 | `date`        | String | YYYY-MM-DD (GMT)             | Calendar date (string form of #5) |
| 7 | `time`        | String | HH:MM:SS (GMT)               | Time of day (string form of #5) |

**Note**: GeoLife data collected GPS trajectories by 182 users in a period from April 2007 to August 2012.

### **Transportation-mode label file** (`labels.txt`)

| # | Column name  | Type     | Format                    | Description |
|---|--------------|----------|---------------------------|-------------|
| 1 | `start_time` | Datetime | YYYY/MM/DD HH:MM:SS (GMT) | Segment start |
| 2 | `end_time`   | Datetime | YYYY/MM/DD HH:MM:SS (GMT) | Segment end |
| 3 | `mode`       | String   | walk, bike, bus, car …    | User-annotated mode |

**Note**: 69 users have labeled their trajectories with transportation mode, such as driving, taking a bus, riding a bike or walking. The label files store the transportation mode labels for these users.

---

## Data Characteristics

### **1. Data Stability**

### 1.1 Number of devices per day over time

| Figure | Figure description |
|--------|-------------------|
| ![Daily active devices](figures_geolife/daily_active_device.png) | The horizontal axis is time (date), and the vertical axis is the number of devices with records on the corresponding date. |

<!-- **Comment**: can you change the title of this figure to "Daily Number of Devices", and vertical axis to "Number of Devices" to make it clearer? The word "active" needs explanation if you use it-->

Summary statistics of number of device per day for different years:

| Statistic | Value&nbsp;(all&nbsp;years) | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 |
|-----------|----------------------------|------|------|------|------|------|------|
| Mean | 5.93 | 3.32 | 10.54 | 11.70 | 2.43 | 2.74 | 2.21 |
| Standard deviation | 6.24 | 2.14 | 6.67 | 7.83 | 1.24 | 1.34 | 1.07 |
| Minimum | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 25th percentile | 2 | 2 | 5 | 4 | 2 | 2 | 1 |
| Median | 3 | 3 | 10 | 12 | 2 | 3 | 2 |
| 75th percentile | 8 | 4 | 14 | 17 | 3 | 4 | 3 |
| Maximum | 29 | 11 | 28 | 29 | 8 | 9 | 5 |


**Findings**: The daily number of active devices (devices that have records on the corresponding date) ranges from 1 to 29, with an overall mean of 5.93, a median of 3, an inter-quartile range of 2 to 8, and a standard deviation of 6.24. The yearly averages fluctuate markedly: the mean is 3.32 devices in 2007, rises to 10.54 in 2008 and peaks at 11.70 in 2009, then falls to roughly 2–3 devices per day during 2010–2012, showing that this metric varies substantially over time rather than remaining stable.

### 1.2 Number of records per device per day over time

| Figure | Figure description |
|--------|--------------------|
| ![Avg daily records](figures_geolife/daily_mean_records_per_user.png) | The horizontal axis is the time (date), and the vertical axis is the average daily number of records for devices (user_ids) with records on the corresponding date |

<!-- (**Comment**: title of the figure - Average Daily Number of Records Per Device, vertical axis - Average number of records per device) -->

Summary statistics of number of records per device per day (for all years):

| Statistic | Value&nbsp;(all&nbsp;years) | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 |
|-----------|-----------------------------|------|------|------|------|------|------|
| Mean | 1788.75 |
| Standard deviation | 1985.82 |
| Minimum | 3.00 |
| 25th percentile | 515.50 |
| Median | 1236.00 |
| 75th percentile | 2450.29 |
| Maximum | 20006.00 |

**Findings**: Over all the years, the daily number of records per device ranges from 3 to 20 006, with a mean of 1,788.75, a median of 1,236.00, and an inter-quartile span from 515.50 to 2450.29; the dispersion is captured by a standard deviation of 1 985.82. As illustrated in the figure, the series jumps up and down rather than forming a smooth, flat line—*a variability rooted in the data itself, where 57 % of trajectories last less than one hour and half of the user IDs have a life span shorter than 50 days*.

<!--(**comment**: 1. where are the numbers in the above sentence come from? It seems to me this sentence is talking about temporal sparsity (life span, lasting hour, etc.) for the next section. Here we are talking about the number of records per device per day and check how stable it is. 2. In order to make the format consistent for 1.1 and 1.2, I think maybe it is better to add the statistics for each year as well. Sorry for adding your work.) -->

---

### **2. Temporal Sparsity**

### 2.1 Intra-day Occupancy

**Note**: Intra-day Occupancy

1. Definition?
2. For each 30 minites time slot, we count how many trajectories contain records for the corresponding time slot and plot the percent of the number of trajectories for each time slot to the total number of trajectories. Here trajectory is a sequence of records for a device (user_id) in one day.
3. We do calculation for each year and whole time period (all years).

| Figure | Figure |
|--------|--------|
| ![trajectory_slot_coverage_2007](figures_geolife/trajectory_slot_coverage_2007.png) | ![trajectory_slot_coverage_2008](figures_geolife/trajectory_slot_coverage_2008.png) |
| ![trajectory_slot_coverage_2009](figures_geolife/trajectory_slot_coverage_2009.png) | ![trajectory_slot_coverage_2010](figures_geolife/trajectory_slot_coverage_2010.png) |
| ![trajectory_slot_coverage_2011](figures_geolife/trajectory_slot_coverage_2011.png) | ![trajectory_slot_coverage_2012](figures_geolife/trajectory_slot_coverage_2012.png) |

![trajectory_slot_coverage_hist](figures_geolife/trajectory_slot_coverage_overall.png)

Description of the figures:
The horizontal axis is each number of 30-minute time slots in one day (there are 48 30-minute time slots in one day, ranging from 1 to 48), and the vertical axis is the percent of daily trajectories recorded in the corresponding number of time slots to the total trajectories. We plot the distribution of the intra-day occupancy for each year and whole time period (all years).

Summary statistics of Intra-day occupancy: number of time slots in one day (slot size = 30 min, total 48 slots in one day)

| Statistic | All years | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 |
|-----------|-----------|------|------|------|------|------|------|
| Mean | 7.60 | 5.20 | 7.43 | 9.35 | 5.64 | 5.50 | 5.06 |
| Standard deviation | 6.31 | 4.41 | 6.05 | 6.94 | 4.67 | 5.31 | 4.69 |
| Minimum | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 25th percentile | 3 | 2 | 3 | 4 | 3 | 2 | 2 |
| Median | 6 | 4 | 6 | 8 | 4 | 4 | 4 |
| 75th percentile | 10 | 7 | 10 | 13 | 7 | 6 | 6 |
| Maximum | 48 | 29 | 46 | 48 | 33 | 39 | 35 |

<!--(Please add some findings from the statistics, following are some examples)-->

**Findings**: We foud that the median was 6 slots for all years data, indicating that half of the trajectories had no more than 3 hours within a day; year 2008 and 2009 have higher intra-day occupancy, with average 7.4 slots (3.7 hours) and 9.4 slots (4.7 hours) within a day, respectively. 


### 2.2 Inter-day Occupancy

**Note**: Inter-day Occupancy

1. Definition?
2. The GeoLife data was collected from April 2007 to August 2012 (total xxx days), thus the inter-day occupancy we calculated for all years are out of the total xxx day, for 2007 and 2012 it is out of a partial year for 2007 (xxx days) and 2012 (xxx days), and for the other years (2008-2011), it is out of full one year.

| Figure | Figure |
|--------|--------|
| ![inter_day_span_distribution_2007](figures_geolife/inter_day_span_distribution_2007.png) | ![inter_day_span_distribution_2008](figures_geolife/inter_day_span_distribution_2008.png) |
| ![inter_day_span_distribution_2009](figures_geolife/inter_day_span_distribution_2009.png) | ![inter_day_span_distribution_2010](figures_geolife/inter_day_span_distribution_2010.png) |
| ![inter_day_span_distribution_2011](figures_geolife/inter_day_span_distribution_2011.png) | ![inter_day_span_distribution_2012](figures_geolife/inter_day_span_distribution_2012.png) |

![inter-day hist across 2007-2012](figures_geolife/inter_day_span_distribution.png)

<!--(**comment**: can you add the total number of days for each year and all years (2007 and 2012 are partial year) to the figures, and also to the summary statistics)-->

Description of the Figure:
The horizontal axis is the number of days each device (user_id) was observed during a specific time period (e.g., one year), and the vertical axis is the percent of the number of device (user_ids) with the corresponding value in number of days observed to the total number of devices (user_ids).

Summary statistics of Inter-day occupancy: number of days observed per device during a specific time period

| Statistic | All years | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 |
|-----------|-----------|------|------|------|------|------|------|
| Total number of days| ? | ? | 366 | 365 | 365 | 365 | ? |
| Mean | 174.41 | 41.57 | 99.88 | 106.29 | 98.22 | 92.00 | 134.80 |
| Standard deviation | 318.56 | 64.25 | 91.47 | 96.83 | 124.71 | 96.56 | 62.64 |
| Minimum | 1 | 1 | 1 | 1 | 1 | 1 | 41 |
| 25th percentile | 11 | 9 | 38 | 15 | 20.25 | 12 | 120 |
| Median | 71 | 12 | 70 | 83 | 29 | 68 | 135 |
| 75th percentile | 167.50 | 32 | 123 | 165 | 132.75 | 125 | 169 |
| Maximum | 1 934 | 242 | 350 | 365 | 365 | 365 | 209 |

<!--(Please add some findings from the statistics, following are some examples)-->

**Findings**: As seen in the figure (for all years), most of the IDs were observed for about xxx days during the time period of xxx days: 75% percent of devices were observed fewer than 168 days in the xxx day period. We foud that year 2009 and 2012 have higher inter-day occupancy, average xxx days out of xxx days in 2009 and average xxx days out of xxx days in 2012.

---

### **3. Spatial Sparsity (spatial gap)**

| Figure | Figure description |
|--------|------------------|
| ![Gap histogram](figures_geolife/spatialgap.png) | The horizontal axis represents the distance (in meters) between two adjacent records, and the vertical axis represents the number of records with the corresponding distance. (The upper bound of the horizontal axis is set at the 95th percentile of the gap distribution.) |

Summary statistics of spatial gaps (meters)

| Statistic | Value (meters) |
|-----------|-----------|
| Mean | 73.24063 |
| Standard deviation | 11 919.00 |
| Minimum | 0 |
| 25th percentile | 2.369673 |
| Median | 8.731946 |
| 75th percentile | 17.64321 |
| 95th percentile |     |
| Maximum | 11 129 650 |

<!-- (**Comment**: can you add the value of 95th percentile? as the upper bound of the horizon axis) -->

**Findings**: The spatial gap distribution is strongly right-skewed: the mean distance between consecutive GPS points is about 73 m, yet the standard deviation exceeds 11 km. The 25th, 50th, and 75th percentiles are roughly 2.4 m, 8.7 m, and 17.6 m, respectively, indicating that three-quarters of gaps are below 18 m. The minimum gap is 0 m, whereas the maximum exceeds 11 000 km, revealing the presence of a small number of extreme long-distance intervals within the data.

---

### **4. Sampling Rate (temporal gap)**  

| Figure | Figure discription |
|--------|-----------------------------|
| ![Gap-time histogram](figures_geolife/temporal_gap_up_to_99th_pct.png) | The horizontal axis represents the temporal gap value (in seconds), and the vertical axis represents the number of records corresponding to the temporal gap value. (The upper bound of the horizontal axis is set at the 99th percentile of the gap distribution.)|

Summary statistics of temporal gaps (seconds)

| Statistic | Value (seconds) |
|-----------|-----------------|
| Mean | 109.61 |
| Standard deviation | 46652.38 |
| Minimum | 0 |
| 25th percentile | 1 |
| Median | 2 |
| 75th percentile | 5 |
| 95th Percentile |   |
| Maximum | 125 739 400 |

<!-- (**Comment**: 1. can you add the value of 95th percentile? 2. for the below findings, add something like "95 percent of the records have a temporal gap of 5 seconds or less, indicating a generally high sample rate in the data." to evaluat the sample rate of geolife data) -->

**Findings**: The temporal gaps between consecutive observations range from 0 to 125 739 400 seconds. Half of the gaps are no longer than 2 seconds, and three-quarters fall within 5 seconds, yet the mean rises to about 110 seconds because a small number of extreme gaps heavily inflate the average; this right-skewed pattern is further reflected in the large standard deviation of roughly 46 652 seconds and the very high maximum value. 

### **5. Precision**
The spatial accuracy (radius) information is not provided in the GeoLife data, so the spatial precision of the data is unknown.

---
