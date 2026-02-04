# Benchmark: STP vs. MLLS in p53 Boolean Networks
### Project Objective: Compare the computational scalability of the Semi-Tensor Product (STP) method against Multivariate Least Squares (MLLS) approximation using DepMap CRISPR dependency data.

1. Data Source

	CRISPR Scores: DepMap Public 25Q3 (Chronos).

	Binarization: Genes are considered "Essential" (State 0) if θ ≤ −1.0.

2. Network Topology

	We utilize the 4-node p53-Mdm2 regulatory graph from the Abou-Jaoudé et al. (2016) model.

	Logic: The connections (Activations/Inhibitions) define the Boolean rules used for the STP transition matrix L.

	Complexity: This 4-node model creates a $2^{4} = 16$ dimensional state space.

3. Methodology

	PCA Weighting: Identify high-variance genes to justify node inclusion.

	STP Calculation: Compute the exact algebraic transition matrix (O($2^{2n}$)).

	MLLS Approximation: Perform linear regression to predict phenotypic outcomes.

	Stress Test: Increase node count until STP reaches the computational breaking point (MemoryError).
