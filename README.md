# Inband_telemetry_design

This project offers a solution for estimating the necessary number of packets to effectively gauge various network delays, including queuing, transmission, and propagation. It further facilitates decision-making processes for determining the nearest Data Center (DC) and the optimal path with the lowest latency.
Two illustrative examples are provided within the repository:
1. **Cochrams_ofc_example_3paths.ipynb**: This example focuses on calculations involving three distinct paths.
1. **Cochrams_ofc_example_Milano.ipynb**: This example enables topology calculations for the entire network, allowing the determination of the closest National Central Office (CO) for each Local CO based on minimal latency.

## Simulation Model
The simulation leverages the M/M/1 model within Kendall's notation. To execute the simulation, the program requires an input file **Metro_topology_full_Milano.xlsx** which contains topology information about links and nodes. 
Input parameters include link capacity (fixed at 10 Gbps), packet size (set at 1250 bytes), the population size for simulation (denoted as "pop_number" with a default of 50,000 samples), and the number of experiments for population analysis (represented by "n_exp" with a default value of 100).

## Simulation process
The simulation begins by randomly generating link loads within the range of 0.1 to 0.8. 
Subsequently, it calculates the theoretical traffic and delays across each link based on these generated loads. Afterwards, the program simulates delays for 50,000 packets along each path.

## Analysis
### Threshold Definition
In preparation for subsequent calculations, the threshold has been defined at 82 microseconds (modifiable through the "threshold_us" variable).

### Results

The program conducts calculations for different sample sizes, including 5, 10, 50, 100, and 400 packets, each corresponding to a Confidence Level of 95% with margin values of 44%, 31%, 14%, 10% and 5% respectively.

The output includes the heatmaps of results, where each path satisfies (or not) the threshold from each ACO (Access Central Office) to each MACO (Metro Aggregation Central Office) across the scenario of the sample size of 5 packets, and 100 packets. The results are calculated with the 82 $\mu s$ threshold and a 99% packet percentage, indicating that 99% of sampled packets within a given path must fall below the threshold to fulfill the specified requirement.

Additionally, certain results on the heatmap are highlighted with red and blue points, indicating instances where the outcome does not align with the original result obtained for the entire population.

