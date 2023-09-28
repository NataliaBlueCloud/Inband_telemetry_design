# Inband_telemetry_design

This project offers a solution for estimating the necessary number of packets to effectively gauge various network delays, including queuing, transmission, and propagation. It further facilitates decision-making processes for determining the nearest Data Center (DC) and the optimal path with the lowest latency.
Two illustrative examples are provided within the repository:
1. **Cochrams_ofc_example_3paths.ipynb**: This example focuses on calculations involving three distinct paths.
1. **Cochrams_ofc_example_Milano.ipynb**: This example enables topology calculations for the entire network, allowing the determination of the closest National Central Office (CO) for each Local CO based on minimal latency.

## Simulation Model
The simulation leverages the M/M/1 model within Kendall's notation. To execute the simulation, the program requires an input file **Metro_topology_full_Milano.xlsx** which contains topology information about links and nodes. 
Input parameters include link capacity (fixed at 10 Gbps), packet size (set at 1250 bytes), the population size for simulation (denoted as "pop_number" with a default of 50,000 samples), and the number of experiments for population analysis (represented by "n_exp" with a default value of 100).

## Simulation Process
The simulation begins by randomly generating link loads within the range of 0.1 to 0.8. 
Subsequently, it calculates the theoretical traffic and delays across each link based on these generated loads.


## Analysis
### Threshold Definition

For effective calculations, it is essential to specify a threshold value for each Local CO in microseconds (us). 
The program provides feedback after execution the results section, indicating whether it is excessively low or high and for which Local CO.
If packet delays originating from a specific Local CO to all nodes (National COs) fall below the defined threshold, it becomes impracticable to define which National CO has the lowest delays.
As well as, if all data surpasses the threshold.

### Results

The program conducts calculations for different sample sizes, including 10, 41, 164, and 452 packets, each corresponding to a Confidence Level of 80% with margin values of 21%, 10%, 5%, and 3% respectively.
The output includes the percentage of data falling below the threshold, enabling the identification of closest National COs (with the highest percentage of values) based on latency.

This project serves as a valuable tool for network latency estimation and decision-making and desing processes, aiding in the optimization of network traffic routing and Data Center selection.


