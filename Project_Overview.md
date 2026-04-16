# Deadlock Detection Simulator – Project Overview

## 1. Purpose

This project is a web-based Deadlock Detection Simulator that helps students understand how deadlocks form and how they can be detected in operating systems.  
Users can:

- Choose the number of processes and resources
- Enter Allocated, Requested / Max, and Available matrices
- Run a detection algorithm to check if the system is in a safe state or deadlocked

The tool supports:
- **Single-instance resources** (Allocated + Requested + Available)
- **Multi-instance resources** (Max + Allocated + Available)

---

## 2. High-Level Workflow

1. User selects **mode**, number of **processes**, and number of **resources**.
2. User clicks **Configure Scenario** – input tables are generated.
3. User fills:
   - Single mode: Allocated, Requested, Available
   - Multi mode: Max, Allocated, Available
4. On **Detect Deadlock**, the script:
   - Validates the matrices
   - Runs the appropriate detection logic
   - Produces:
     - Result (Safe / Deadlock)
     - Step-by-step execution log
     - Resource Allocation Graph (in single-instance mode)

---

## 3. Algorithms Used

- **Single-instance mode**
  - Uses a Wait-For / Resource Allocation Graph style approach.
  - If no process can proceed with the currently available resources and some processes are unfinished, those unfinished processes are considered deadlocked.

- **Multi-instance mode**
  - Uses a Banker-style safety check:
    - Need = Max – Allocated
    - If no unfinished process’s Need can be satisfied by Available, the remaining processes are in deadlock.

---

## 4. Files

- `Index.html` – Main UI and layout
- `styles.css` – Dark theme and styling
- `script.js` – Deadlock detection logic, validation, visualization
- `PROJECT_OVERVIEW.md` – This documentation file
- `flow_simple.txt` – Text flow of the simulator logic
- `scenarios/` – Example JSON scenarios (safe and deadlocked)
