# Citi Bike
The goal is to build a discrete-event simulation to study Citi Bike, New York City's bike-share service, and determine the number of bikes the city needs to allocate to each station in order to meet demand while minimizing costs.

The simulation models travel between $m$ predefined stations throughout one logical day (24 hours). Each station is modeled as an elementary queue.
The parameters of the simulation are outlined below:
1. **NUM_RIDERS**: the number of riders that will arrive throughout the day
2. **LAMBDA**: the interarrival times of the riders are determined via an autonomous, stationary, and independent stochastic process, following an exponential distribution with rate LAMBDA
3. Each rider selects a starting station randomly based on probabilities enumerated in **data\start_station_probs.csv**
4. Each rider selects a destination station randomly based on trip counts outlined in **data\trip_stats.csv**
5. **MU**, **SIGMA**: the amount of time the riders use their bikes for follows a log-normal distribution with mean MU and standard deviation SIGMA
6. **STATION_CAPACITY**: at the beginning of the simulation, each station is populated with STATION_CAPACITY bikes -- if there are no bikes left at a station, riders wanting to check out a bike from the station must wait until a bike is returned to the station
7. **IDEALIZED**: if true, then there can be no more than STATION_CAPACITY bikes parked at a station -- if the station is at capacity, riders wanting to return a bike to the station must wait until a bike is checked out from the station
8. **VERBOSE**: whether or not the user wants a detailed summary of simulation events and states

At the end of the simulation, statistics are calculated for the likelihood of a successful bike rental, the likelihood of a successful bike return, and the average time riders wait to check out a bike.