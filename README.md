# Classical Social Network Generators in Julia

This project re-implements four classical network generation algorithms in Julia from scratch, based on their original specifications. This provides a well-documented and reproducible implementations of these models, separate to the ones found in the Graphs.jl package.

## Algorithms Implemented

### Erdős–Rényi (1960)
Generates random graphs by connecting each pair of nodes with a fixed probability *p*. A foundational model in random graph theory.

> Erdős, P. and Rényi, A. (1960). On the evolution of random graphs. *Publications of the Mathematical Institute of the Hungarian Academy of Sciences*, 5, 17–60.

### Watts–Strogatz (1998)
Generates small-world networks characterised by high clustering coefficient and short average path lengths, by rewiring edges of a regular lattice with probability *p*.

> Watts, D.J. and Strogatz, S.H. (1998). Collective dynamics of 'small-world' networks. *Nature*, 393, 440–442.

### Barabási–Albert (1999)
Generates scale-free networks through preferential attachment, where new nodes are more likely to connect to already well-connected nodes, producing degree distributions following a power law.

> Barabási, A.L. and Albert, R. (1999). Emergence of scaling in random networks. *Science*, 286(5439), 509–512.

### Molloy–Reed / Configuration Model (1995)
Generates random graphs with a specified degree sequence, connecting pairs of edges. The sum of degrees (from the degree sequence) must be even or otherwise it is not realisable.

> Molloy, M. and Reed, B. (1995). A critical point for random graphs with a given degree sequence. *Random Structures and Algorithms*, 6, 161–179.

## Repository Structure

├── LICENSE
├── README.md
├── network_generators.jl  # Implementation of all four classical network generation algorithms
└── network_properties.jl  # Function to compute and analyse structural network properties

## Network Properties Computed

These are: all four network centrality measures (degree, closeness, betweenness and eigenvector) and corresponding measure of inequality (Gini coefficient), clustering coefficient (local and global/transitivity, average path length/mean geodesic and network diameter.

## How to Run

### Prerequisites
Julia 1.x or above. Install required packages by running:

```julia
using Pkg
Pkg.add(["Graphs", "Random", "Statistics", "Inequality", "DataFrames", "CSV"])
```
### Usage

```julia
include("network_generators.jl")
include("network_properties.jl")

# Example: Generate an Erdős–Rényi random graph
# with 100 nodes and connection probability 0.05
g = ER_model(100, 0.05)

# Example: Generate a Watts–Strogatz small-world network
# with 100 nodes, 4 nearest neighbours, rewiring probability 0.1
g = WS_model(100, 4, 0.1)
```

## Motivation

These implementations were developed as part of a broader research project looking at realistic synthetic social network generation for agent-based simulation models during my research associate position at Durham University (2023–2026) in collaboration with Dr. Jen Badham.

## Related Projects

- [Social Circles](https://github.com/chuecadelc/Parameterising_Social_Circles_generator) — we assess the suitability of this distance-based network generator originally created by Hamil and Gilbert (2009) as a generalisable network generator.

## Author
Find out more about my work in my [Portfolio](chuecadelc.github.io)
