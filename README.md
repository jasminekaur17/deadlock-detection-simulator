# Deadlock Detection Simulator

> An interactive web-based simulator for understanding, testing, and visualizing deadlock detection concepts in operating systems.

---

## Overview

The **Deadlock Detection Simulator** is an educational and interactive project built to help users understand how deadlocks arise in operating systems and how they can be detected under different resource-allocation models.

It allows users to configure processes, resources, and matrices, then runs the detection logic to determine whether the system is in a **safe state** or a **deadlock state**. The project emphasizes **clarity**, **visual learning**, and **step-by-step analysis**.

---

## Why This Project?

Deadlock detection is often difficult to grasp through theory alone. This simulator bridges that gap by offering:

- Interactive scenario creation
- Matrix-based input handling
- Step-by-step detection flow
- Visual representation of resource relationships
- Easy experimentation with safe and deadlocked cases

---

## Key Features

- **Single-instance deadlock detection**
- **Multi-instance deadlock detection**
- Dynamic selection of:
  - Number of processes
  - Number of resource types
- Automatic matrix generation
- Step-by-step execution tracing
- Resource Allocation Graph (RAG) visualization in single-instance mode
- Scenario import/export using JSON
- Reset and reconfiguration support
- Clean and responsive dark-themed interface

---

## Operating Modes

### 1. Single-Instance Mode

This mode is designed for systems where each resource type has only **one instance**.

**Uses:**
- Allocated matrix
- Requested matrix
- Available matrix

**Detection idea:**
- A process can proceed only if its requested resources are available
- If no process can proceed and circular waiting exists, the system is deadlocked

---

### 2. Multi-Instance Mode

This mode works for systems where each resource type may have **multiple instances**.

**Uses:**
- Max matrix
- Allocated matrix
- Available matrix

**Detection idea:**
- Evaluates whether a safe execution order exists
- If no safe sequence can be formed, the system is considered deadlocked

---

## How the Simulator Works

```text
Start
  |
Select mode
  |
Enter number of processes and resources
  |
Generate scenario matrices
  |
Fill matrix values
  |
Run deadlock detection
  |
Check if a process can proceed
  |
Repeat until all possible processes finish
  |
Safe state? ---- Yes ---> Show safe sequence
  |
  No
  |
Show deadlock result
  |
End
```

---

## Detection Logic Summary

### For Single-Instance Systems
The simulator checks whether processes can complete using currently available resources. If all remaining processes are waiting indefinitely with no progress possible, a deadlock is detected.

### For Multi-Instance Systems
The simulator applies a safety-check approach similar to the logic used in resource-allocation analysis. It verifies whether all processes can complete in some valid order.

---

## Educational Value

This project is useful for:

- Operating Systems laboratory work
- Academic demonstrations
- Viva preparation
- Understanding deadlock concepts visually
- Comparing safe and unsafe system states

---

## Technology Stack

### Frontend
- **HTML**
- **CSS**
- **JavaScript**

### Visualization / Utilities
- **vis-network.js** for graph-based visualization
- **JSON** for scenario import/export

---

## Project Structure

```text
deadlock-detection-simulator/
│
├── index.html
├── styles.css
├── script.js
├── README.md
├── PROJECT_OVERVIEW.md
├── flow_simple.txt
├── scenarios/
│   ├── deadlock_example_single.json
│   └── safe_example_single.json
└── LICENSE
```

---

## Sample Deadlock Example

A deadlock may occur in single-instance mode like this:

- **P0** holds **R0** and requests **R1**
- **P1** holds **R1** and requests **R2**
- **P2** holds **R2** and requests **R0**
- No additional resources are available

This creates a **circular wait**, so none of the processes can continue.

---

## Expected Outcomes

By using this simulator, a user should be able to:

- Understand how deadlocks occur
- Differentiate between safe and unsafe states
- Learn how detection algorithms work
- Visualize process-resource dependency
- Experiment with custom scenarios easily

---

## Future Improvements

Some possible enhancements for this project include:

- Deadlock recovery suggestions
- Deadlock avoidance simulation
- Distributed deadlock detection models
- More advanced visual analytics
- Performance statistics for larger scenarios
- Better UI animations and reporting panels

---

## References

- Silberschatz, Galvin, Gagne — *Operating System Concepts*
- Standard Operating Systems course materials
- Deadlock detection and resource-allocation model references
- vis-network.js documentation

---

## 🚀 Project Repository

Explore the complete source code and project files:

🔗 https://github.com/jasminekaur17/deadlock-detection-simulator

> Repository: deadlock-detection-simulator

## Final Note

This simulator is designed to make a core operating systems concept easier to explore, test, and understand through direct interaction. It combines theory with visualization to create a more practical learning experience.
