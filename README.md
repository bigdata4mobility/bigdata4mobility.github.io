## A brief introduction of various datasets for transportation applications


| Dimensions      | Household travel survey | Online panels | LBS mobile data | Traffic counts | Smart card data |
| :---        |    :----   |  :--- |   :--- |  :---  | :--- |
| Generation      | active | active   | passive |
| Key data items  | trips made in a day by subjects | general travel behavior  | network interaction events| number of moving objects at a location during a time interval | a tap in the system |
| Sampling method | probabilistic | non-probabilistic | non-probabilistic | non-probabilistic | non-probabilistic |
| Sampling rate | low | varied | high | varied | high |
| Richness | rich | rich | shallow | shallow | shallow |
| quality | high | varied | high precision and sparsity | varied | varied |
| Spatial coverage | small | varied | large | varied | varied |
| Temporal coverage | snapshot | snapshot | continuous | continuous | continuous |
| Capturing O-D patterns | yes | no | no | no | yes |
| Cost | high | moderate | low | low | low |
| Generalizability | high | low | varied | varied | varied |
| Pre-processing required | light | light | heavy | low | varied |
| Long-term policy analysis | good | good | poor | poor | poor |
| Short-term  policy analysis | poor | poor | good | good | good |

**An important note** is that while traditional datasets such as  household travel surveys and traffic counts directly provide us with transportation related information (trips subjects made in a day for household travel survey data and number of moving objects at a location during a time interval for traffic count data), big mobile data does not contain information directly about people's travel patterns. Instead, it contains information that reflects people's usage with their mobile phones. In this case, each record in the big mobile data represents an instance that the device communicates with the network at where and when. 


## Describe data

![BostonData](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/describe-data-boston.png)
#### A snapshot of the big mobile data

## Data stability
![stability](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-stability-seattle.jpg)
#### Changes in the number of devices (individuals) over time in the Seattle area

![stability](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-stability-seattle2.jpg)
#### Changes in the number of records per device (individual) over time in the Seattle area

![stability](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-stability-boston.png)
#### Changes in the number of records per device (individual) over time in the Boston area

## Data quality metrics by region types
![quality-metrics](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/data-quality-metrics-by-region-type.png)
#### Data quality metrics by region type

![quality-metrics](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/biases-in-mobility-metric-by-region-type.png)
#### Biases in various mobility metrics by region type (bias is calculated as the absolute percentage difference from the metric calculated from the 2017 NHTS data

## Effects of oscillation
![oscillation](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-oscillation.png)
#### Effect of not removing oscillation on a single trajectory

![oscillation](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-pre-or-post-oscillation-treatment.jpg)
#### Effect of treating oscillation before or after pre-processing the trajectory data

## Effects of pre-processing algorithms
![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm.png)
#### Effect of pre-processing algorithm on a single trajectory using the same distance and time thresholds

![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm-on-mobility-metric.png)
#### Effect of pre-processing algorithm on different mobility metrics

![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm-components-on-trips.jpg)
#### Effect of pre-processing algorithm components on number of trips

![algorithm](https://github.com/bigdata4mobility/bigdata4mobility.github.io/blob/main/assets/effect-of-algorithm-components-on-ROG.jpg)
#### Effect of pre-processing algorithm components on radius of gyration