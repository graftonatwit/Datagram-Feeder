# Datagram-Feeder
Datagram Feeder
Overview

Datagram Feeder is a Python script that generates dummy datagram arrivals for router simulations.
Each datagram contains:

<arrival_time_ms> <flow_id> <priority> <size_bytes> <payload>

It supports multiple flows, bursts, and configurable priority assignment policies.

Features

Generate simulated datagrams for testing routers or network algorithms.

Configurable rate, burst size, flows, simulation duration, and priority assignment policy.

Real-time pacing with optional reproducibility using random seeds.

Supports three priority policies:

random – assign priorities randomly between 0–3.

by_flow – assign priorities based on flow ID.

uniform – assign the same priority to all datagrams.

Installation

Requires Python 3.x (no additional packages needed).

Clone the repository:

git clone <your-repo-url>
cd <repository-folder>
Usage
python3 datagram_feeder.py --rate 10 --burst 4 --flows 3 --duration 5 --policy random --seed 42
Options
Option	Description	Default
--rate	Average datagram rate per second	10
--burst	Number of datagrams per burst	1
--flows	Number of flows	1
--duration	Duration of the simulation in seconds	5
--policy	Priority assignment policy: random, by_flow, uniform	random
--seed	Optional random seed for reproducibility	None
Example Output
0.0 2 1 512 DATA_1
0.0 1 0 1024 DATA_2
100.0 3 3 1500 DATA_3
...
# END

Each line represents a datagram with arrival time (ms), flow ID, priority, size (bytes), and payload.

# END marks the end of the simulation.

Notes

The script simulates real-time arrivals using time.sleep.

Inter-arrival times are constant; for more realistic traffic, you could modify it to use Poisson-distributed times.

Burst mode allows sending multiple datagrams at the same simulated timestamp.

Author

Trevor Grafton

Simulates datagram traffic for network research, testing, or educational purposes.
