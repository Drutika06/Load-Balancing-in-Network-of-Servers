## Job Migration Minimization using Breadth-First Search (BFS)
This project simulates and solves the problem of minimizing job migrations in a capacity-constrained computer network, modeled after a university data center. When a new job is submitted to a node that is at full capacity, this algorithm finds the nearest available node in the network to process the job, thereby minimizing the total number of migrations. The core of the solution is the Breadth-First Search (BFS) algorithm.

## Problem Description
In a network of computer systems (nodes), each node has a predefined maximum capacity (weight) representing the number of applications it can execute simultaneously. These nodes are interconnected, forming a graph.

Nodes: Represent individual computer systems.
Node Weight: The maximum job capacity of a system.
Edges: Represent a direct connection between two systems.
Migration: The transfer of a job from one node to an adjacent node.

When a new job is submitted to a node that is already at full capacity, it must be migrated to a connected node. The goal is to find a path to a node with available capacity that requires the minimum number of migrations.

Example Scenario:
Consider the graph below. Node N2 has a capacity of 4 and is currently processing 4 jobs (J5, J6, J7, J8). If a new job, J14, is submitted to N2, it cannot be processed there. The algorithm must decide whether to migrate it to N1 or N4 to find the closest available server.

## Algorithm: Breadth-First Search (BFS)
We use Breadth-First Search (BFS) because it is guaranteed to find the shortest path in terms of the number of edges (or "hops") in an unweighted graph. Since each migration corresponds to traversing one edge, BFS is the perfect algorithm to find the node that requires the fewest migrations.

The algorithm works as follows:
Job Submission: A new job arrives at a specific source node.
Capacity Check: The algorithm first checks if the source node has available capacity.
If yes, the job is assigned to the source node. Total Migrations: 0.
If no, the node is at full capacity, and a migration is necessary.
Initiate BFS: A BFS is initiated starting from the source node to find the nearest neighbor with free capacity.
A queue is used to keep track of nodes to visit, starting with the source node's immediate neighbors.
A visited set is used to avoid cycles and redundant processing.
Level-by-Level Search: BFS explores the graph layer by layer:
It first checks all immediate neighbors (1 migration).
If no capacity is found, it then checks their neighbors (2 migrations), and so on.
Find Destination: The first node discovered during the search that has available capacity is the optimal destination. The distance from the source node to this destination node gives the minimum number of migrations required.
No Capacity: If the BFS completes and all reachable nodes have been visited without finding one with available capacity, the job cannot be placed in the network.


<img width="964" height="748" alt="image" src="https://github.com/user-attachments/assets/c42db846-66a4-4e11-91c9-066ede9e23fb" />
<img width="597" height="934" alt="image" src="https://github.com/user-attachments/assets/028f246e-b0a6-45fa-a368-62ad78b551fe" />

