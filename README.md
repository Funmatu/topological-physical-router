# Topological vs. Physical Routing Simulation

This repository contains a Python simulation designed to bridge the gap between **Mathematical Topology** and **Physical Engineering Reality** in the context of routing problems (e.g., PCB design, cable management, multi-agent path finding).

It visually demonstrates why a connection that is "theoretically possible" (topologically planar) often fails in the real world due to physical constraints like line width and clearance.

## 🎯 Purpose & Intent

The primary goal of this project is to provide a learning platform that simultaneously verifies:
1.  **Theoretical Solvability:** Is the graph planar? Are there fundamental topological knots (entanglements)?
2.  **Physical Feasibility:** Can valid paths be found when lines have width and cannot overlap?

By comparing these two perspectives side-by-side, users can understand the complexity of routing algorithms and the impact of geometric constraints on topological problems.

## 🚀 Key Features

### 1. Mathematical Topology (Theoretical View)
-   **Graph Planarity Test:** Uses `NetworkX` to determine if the connection graph is planar (Kuratowski's theorem).
-   **Algebraic Topology:** Projects points onto the boundary to calculate the **Intersection Matrix** and **Crossing Number**, identifying intrinsic entanglements.
-   **Geometric Intersection:** Checks for simple straight-line intersections.

### 2. Physical Reality (Engineering View)
-   **Grid-Based A* Search:** Implements the A* algorithm considering **Line Width** and **Clearance**.
-   **Permutation Search:** Iterates through all possible wiring orders to find a valid solution, avoiding deadlocks caused by "greedy" routing.
-   **Collision Avoidance:** Simulates realistic obstacles where existing paths become walls for subsequent connections.

## 🛠️ Environment & Requirements

This script is designed to run seamlessly on **Google Colab**.

### Dependencies
-   `python >= 3.7`
-   `numpy`
-   `matplotlib`
-   `networkx`

*(Note: Standard Colab environments include these libraries by default.)*

## 📖 Usage

1.  Clone this repository or copy the script to a Google Colab notebook.
2.  Run the script. It will generate a random scenario with 4 pairs of points.
3.  The output will display:
    -   **Console Report:** Solvability status from both mathematical and physical perspectives.
    -   **Dual Visualization:** -   *Left:* Geometric/Topological view (straight lines).
        -   *Right:* Physical simulation view (actual routed paths with width).

## 🧩 Visualization Example

-   **Mathematical View:** Shows points and straight lines. If the Crossing Number is 0, the problem is topologically trivial.
-   **Physical View:** Shows the actual routed paths avoiding obstacles. If "Blocked", it indicates that physical constraints (density, bottlenecks) prevented a solution despite theoretical possibilities.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
