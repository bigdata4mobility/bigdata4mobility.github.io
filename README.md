## A brief introduction of various datasets for transportation applications


| Dimensions      | Household travel survey | Traffic counts | Big mobile data |
| :---        |    :----   |          :--- |   :--- |
| Generation      | actively collected by asking people trips they made in a day | actively collected by installing sensors that record the number of moving objects   | passively collected by records users' interaction with mobile apps |
| What is in the data   | all trips and their characteristics a subject made in a day | number of moving objects at a location during a time interval  | each record represents an event that records the location (lat and long) and time when a device is observed on the network |
| Sampling rate | low | varied | high |
| Sampling method | probabilistic | non-probabilistic | non-probabilistic |

**An important note** is that while traditional datasets such as  household travel surveys and traffic counts directly provide us with transportation related information (trips subjects made in a day for household travel survey data and number of moving objects at a location during a time interval for traffic count data), big mobile data does not contain information directly about people's travel patterns. Instead, it contains information that reflects people's usage with their mobile phones. In this case, each record in the big mobile data represents an instance that the device communicates with the network at where and when. 


## Describe data

![BostonData](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/describe-data-boston.png)
####Changes in the number of records per device over time in the Boston area

## Data stability
![stability](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-stability-seattle.jpg)
*Changes in the number of devices (individuals) over time in the Seattle area*

![stability](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-stability-seattle2.jpg)
*Changes in the number of records per device (individual) over time in the Seattle area*

![stability](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-stability-boston.png)
*Changes in the number of records per device (individual) over time in the Boston area*

## Data quality metrics by region types
![quality-metrics](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-quality-metrics-by-region-type.png)
*Data quality metrics by region type*

![quality-metrics](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/biases-in-mobility-metric-by-region-type.png)
*Biases in various mobility metrics by region type (bias is calculated as the absolute percentage difference from the metric calculated from the 2017 NHTS data*

## Effects of oscillation
![oscillation](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-oscillation.png)
*Effect of not removing oscillation on a single trajectory*

![oscillation](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-pre-or-post-oscillation-treatment.png)
*Effect of treating oscillation before or after pre-processing the trajectory data*

## Effects of pre-processing algorithms
![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm.png)
*Effect of pre-processing algorithm on a single trajectory using the same distance and time thresholds*

![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm-on-mobility-metric.png)
*Effect of pre-processing algorithm on different mobility metrics*

![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm-components-on-trips.png)
*Effect of pre-processing algorithm components on number of trips derived*