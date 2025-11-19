# DSC212: Karate Club Modularity Assignment

[cite_start]This repository contains the solution for the "Modularity on the Karate Club Graph" assignment for the DSC212: Graph Theory Module. [cite: 2]

## 🎯 Overview

[cite_start]The goal of this project is to implement a community detection algorithm based on **spectral modularity maximization** and apply it to the classic **Zachary's Karate Club network**. [cite: 8, 15] [cite_start]The assignment requires a "from-scratch" implementation of the recursive bisection method described by Newman (2006) to uncover the social "fault lines" [cite: 24] [cite_start]that led to the club splitting into two factions. [cite: 18, 19]

## 🛠 Methodology

[cite_start]The core of the algorithm is **recursive spectral bisection**. [cite: 119, 153]

1.  [cite_start]**Modularity Matrix (B):** First, the global $n \times n$ modularity matrix for the entire graph is calculated. [cite: 80] The formula for this matrix is:
    $$B = A - \frac{kk^{\top}}{2m}$$
    [cite_start]where $A$ is the adjacency matrix, $k$ is the degree vector, and $m$ is the total number of edges in the graph. [cite: 58, 59]

2.  [cite_start]**Spectral Bisection:** To split any community $C$, we first find the *restricted* modularity matrix $B^{(C)}$ by taking the rows and columns of the global $B$ that correspond to nodes in $C$. [cite: 123, 124]
    * [cite_start]We then find the leading eigenpair $(\lambda_1, u_1)$ of this $B^{(C)}$ matrix. [cite: 127]
    * [cite_start]The community is split into two new groups based on the *sign* of the entries in the leading eigenvector $u_1$. [cite: 115, 159]

3.  [cite_start]**Stopping Criterion:** This recursive process stops splitting a community $C$ if its leading eigenvalue $\lambda_1^{(C)}$ is non-positive (i.e., $\lambda_1^{(C)} \le 0$). [cite: 130, 158] [cite_start]A non-positive eigenvalue indicates that no further split of that community can increase the overall modularity score. [cite: 139, 141]

## ✅ Tasks Completed

[cite_start]This solution successfully completes all tasks specified in the assignment document: [cite: 195-204]

1.  **Task 1 (Implementation):** Implemented the recursive spectral modularity partitioning algorithm.
2.  **Task 2 (Graph Visualization):** Visualized the state of the graph after each successful split, with nodes colored by their new community assignments. [cite_start]A fixed spring layout is used for consistency. [cite: 164]
3.  **Task 3 (Metrics Computation):** After each split, four key node metrics were computed for the nodes *within their new subgraph*:
    * [cite_start]Degree Centrality [cite: 169]
    * [cite_start]Betweenness Centrality [cite: 174]
    * [cite_start]Closeness Centrality [cite: 179]
    * [cite_start]Clustering Coefficient [cite: 184]
4.  **Task 4 (Metric Evolution):** Plotted the evolution of each of these four metrics for every node across the different recursion levels.
5.  **Task 5 (Discussion):** Wrote a final discussion analyzing which nodes remain central and how the community structure influences the metric values.

## 📂 Files in Repository

* **`karate_club_assignment.ipynb`**: The main Jupyter Notebook containing all Python code, step-by-step visualizations, and the final analysis.
* **`README.md`**: This file.

## 📚 Citation

[cite_start]The method implemented is based on the following paper, as required by the assignment: [cite: 150]

> Newman, M. E. J. (2006). Modularity and community structure in networks. *PNAS*, 103(23), 8577-8582.