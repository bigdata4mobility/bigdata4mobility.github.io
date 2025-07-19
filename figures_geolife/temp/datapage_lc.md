# Open Source Dataset: GeoLife

## Data Variables

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

### **Transportation-mode label file** (`labels.txt`)

| # | Column name  | Type     | Format                    | Description |
|---|--------------|----------|---------------------------|-------------|
| 1 | `start_time` | Datetime | YYYY/MM/DD HH:MM:SS (GMT) | Segment start |
| 2 | `end_time`   | Datetime | YYYY/MM/DD HH:MM:SS (GMT) | Segment end |
| 3 | `mode`       | String   | walk, bike, bus, car …    | User-annotated mode |

'mode': 69 users have labeled their trajectories with transportation mode, such as driving, taking a bus, riding a bike or walking. The label files store the transportation mode labels for these users. 

---

## Data Characteristics

### **1. Data Stability**

### 1.1 Number of devices per day over time

| Figure | Figure description |
|--------|-------------------|
| ![Daily active devices](figures_geolife/daily_active_device.png) | The horizontal axis is time (date), and the vertical axis is the number of devices with records on the corresponding date. |

(**Comment**: title of this figure - Daily Number of Devices, vertical axis - Number of Devices)

Summary statistics of number of device per day for different years:

| Statistic | Value (all years) | 2007 | 2008 | 2009 | 2010 | 2011 | 2012 |
|-----------|-------------------|------|------|------|------|------|------|
| Mean | 5.93 |
| Standard deviation | 6.24 |
| Minimum | 1 |
| 25th percentile | 2 |
| Median | 3 |
| 75th percentile | 8 |
| Maximum | 29 |

(**Comment**: Can you also find the statistics for different years to see how it varies in different years?)

The daily number of devices range from 1 to 29; the average is 5.93, the median is 3, the inter-quartile span runs from 2 to 8, and the dispersion is captured by a standard deviation of 6.24.

(**Comment**: you can add something like "The average daily number of devices is not stable over the years, for example, it is xxx in 2008, and up to xxx in 2009, and down to xxx in years 2010-2012." to the above paragraph. The purpose is to find if this number is stable or varies a lot over time.)

### 1.2 Number of records per device per day over time

| Figure | Figure description |
|--------|--------------------|
| ![Avg daily records](figures_geolife/daily_mean_records_per_user.png) | The horizontal axis is the date, and the vertical axis is the average number of records for devices (user_ids) with records on the corresponding date |

(**Comment**: title of the figure - Average Daily Number of Records Per Device, vertical axis - Average number of records per device)

Summary statistics of number of records per device per day (for all years): 

| Statistic | Value |
|-----------|-------|
| Mean | 1788.75 |
| Standard deviation | 1985.82 |
| Minimum | 3.00 |
| 25th percentile | 515.50 |
| Median | 1236.00 |
| 75th percentile | 2450.29 |
| Maximum | 20006.00 |

The daily number of records per device ranges from 3 to 20006, with a mean of 1788.75, a median of 1236.00, and an inter-quartile span from 515.50 to 2450.29; the dispersion is captured by a standard deviation of 1985.82.

(**comment**: You can something like "As we can see from the figure, the daily number of records per device varies a lot over time (jumping up and down freqently instead of a smooth and flat line)" to the above paragraph about the data stability.)

---

### **2 Temporal Sparsity**

### 2.1 Intra-day Occupancy

| Figure | Figure |
|--------|--------|
| ![trajectory_slot_coverage_2007](figures_geolife/trajectory_slot_coverage_2007.png) | ![trajectory_slot_coverage_2008](figures_geolife/trajectory_slot_coverage_2008.png) |
| ![trajectory_slot_coverage_2009](figures_geolife/trajectory_slot_coverage_2009.png) | ![trajectory_slot_coverage_2010](figures_geolife/trajectory_slot_coverage_2010.png) |
| ![trajectory_slot_coverage_2011](figures_geolife/trajectory_slot_coverage_2011.png) | ![trajectory_slot_coverage_2012](figures_geolife/trajectory_slot_coverage_2012.png) |

![trajectory_slot_coverage_hist](figures_geolife/trajectory_slot_coverage_hist.png)


Description of the figures:
The horizontal axis is each 30-minute time slot in one day (there are 48 time slots in one day, ranging from 1 to 48), and the vertical axis is the number (change to "percent") of daily trajectories recorded in the corresponding time slot. We divide the whole time into each year. 

(**Comment**: 1. horizon axis - Number of time slots (slot-size = 30 min), vertical axis - Percent of daily trajectory 2. Can you also find the statistics of this value - number of time slots for a device on one day, so you find the mean, median, different percentiles of this value.)

Summary statistics of Intra-day occupancy (number of time slots in one day (slot size = 30 min))

| Statistic | Value |
|-----------|-------|
| Mean | 
| Std | 
| Min | 
| 25% | 
| 50% (Median) |
| 75% | 
| 90% |
| Max | 

*Description*

Intra-day Occupancy:

1. Trajectory is a sequence of records for a user_id in one day.
2. We do calculation in each year
3. For each 30 minites time slot, we count how many trajectories contain records for the corresponding time slot.

### 2.2 Inter-day Occupancy

| Metric | Figure | Figure description |
|--------|--------|--------------------|
| **Inter-day occupancy** | ![Slot coverage histogram](figures_geolife/inter_day_span_distribution.png) | The horizontal axis is the time range in which each user_id exists, and the vertical axis is the ratio of the number of user_ids with the corresponding value in the existence time to the total number of user_ids. |

(**Comment**: horizontal axis - Number of days observed, vertical axis - Percent of User_IDs, this figure is the Distribution of number of days observed)

(**Comment**: can you also do the inter-day for each year (number of days a user was observed in that year), similar to intra-day? I would like to see how different it is for each year.)

Summary statistics of Inter-day occupancy (number of days observed per device in one year)

| Statistic | Value | 2007 (# days) | 2008 (366 days) | 2009 (365 days) | 2010 (365 days) | 2011 (365 days) | 2012 (# days) |
|-----------|-------|------|------|------|------|------|------|
| Mean | 
| Std | 
| Min | 
| 25% | 
| 50% (Median) |
| 75% |
| 90% | 
| Max | 

*Description*

Inter-day Occupancy:

1. We calculate all the user_id exsisting time 
2. We calculate the ratio of the number of user_ids with the corresponding value in the existence time to the total number of user_ids.


---

### **3 Spatial Sparsity(spatial gap)**

| Figure | Figure description |
|--------|------------------|
| ![Gap histogram](figures_geolife/spatialgap.png) | The horizontal axis represents the distance between two adjacent records, and the vertical axis represents the number of records with the corresponding distance. The upper bound of the horizontal axis is set at the 95th percentile of the gap distribution. |

Summary statistics of spatial gaps (meters)

| Statistic | Value | value |
|-----------|-------|-------|
| Mean | 7.324063 × 10¹ | 73.2 |
| Std | 1.191900 × 10⁴ | 1.2 x 10⁴ |
| Min | 0.000000 × 10⁰ | 0.0 |
| 25% | 2.369673 × 10⁰ | 2.4 |
| 50% (Median) | 8.731946 × 10⁰ | 8.7 |
| 75% | 1.764321 × 10¹ | 17.6 |
| Max | 1.112965 × 10⁷ | 1.1 x 10⁷ |

(**Comment**: I feel like it is easier to read the number in this format)

The spatial gap distribution is strongly right-skewed: the mean distance between consecutive GPS points is about 73 m, yet the standard deviation exceeds 11 km. The 25th, 50th, and 75th percentiles are roughly 2.4 m, 8.7 m, and 17.6 m, respectively, indicating that three-quarters of gaps are below 18 m. The minimum gap is 0 m, whereas the maximum exceeds 11 000 km, revealing the presence of a small number of extreme long-distance intervals within the data.

---

### **4 Sampling Rate (temporal gap)**  

| Figure | Figure discription |
|--------|-----------------------------|
| ![Gap-time histogram](figures_geolife/temporalgap.png) | The horizontal axis represents the temporal gap value, and the vertical axis represents the number of records corresponding to the temporal gap value. The upper bound of the horizontal axis is set at the 95th percentile of the gap distribution.|

(**Comment**: 1. Maybe change the range of the vertical axis to 10 seconds instead of 5? 2. Can you find the statistics of temporal gap as below?)

Summary statistics of temporal gaps (seconds)

| Statistic | Value |
|-----------|-------|
| Mean | 
| Std | 
| Min | 
| 25% | 
| 50% (Median) |
| 75% | 
| Max | 

---
