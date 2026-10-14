# CPU Scheduling Algorithm Comparison System (Java Swing)

An interactive, desktop-based graphical application built using **Java Swing** designed to simulate, visualize, and compare two prominent CPU scheduling algorithms: **Shortest Remaining Time First (SRTF)** and **Round Robin (RR)**.

---

## Overview

Operating systems use scheduling algorithms to manage CPU execution time efficiently across multiple processes. This application allows students, educators, and developers to:
* Input custom processes with varying Arrival Times, Burst Times, and Priorities (where applicable).
* Configure algorithm-specific parameters (like the Time Quantum for Round Robin).
* Run both algorithms side-by-side or individually.
* Visualize process execution over time using dynamic UI charts/gantt charts.
* Analyze and compare key performance metrics: **Waiting Time**, **Turnaround Time**, and **CPU Utilization**.

---

## Key Features

1. **Interactive Graphical User Interface (Java Swing):**
   * Clean form inputs for adding, editing, and deleting processes dynamically.
   * Dedicated configuration panels for Time Quantum adjustments.
   * Real-time validation to catch overlapping arrivals, negative burst times, or empty fields.

2. **Algorithm Implementations:**
   * **Shortest Remaining Time First (SRTF):** The preemptive version of Shortest Job First (SJF). It dynamically switches execution whenever a new process arrives with a shorter remaining burst time than the currently running process.
   * **Round Robin (RR):** A preemptive algorithm that assigns a fixed time unit (Time Quantum) to each process in a cyclic queue, ensuring fair resource allocation.

3. **Comparative Analysis & Metrics:**
   * Calculates and displays **Average Waiting Time (AWT)** and **Average Turnaround Time (ATT)** for both algorithms.
   * Generates comparative performance summaries to highlight which algorithm performs better under specific workloads.

---

## Technical Architecture & Design

* **GUI Framework:** Built on Java AWT/Swing (`JFrame`, `JPanel`, `JTable`, `JScrollPane`, custom paint components for Gantt charts).
* **Object-Oriented Design:** Adheres to clean architecture principles:
  * `Process` model holding core attributes (ID, Arrival Time, Burst Time, Remaining Time, Completion Time, etc.).
  * Dedicated scheduler engine classes handling core logic independently of the UI layer (separation of concerns).
* **Event Handling:** Uses Java ActionListeners and MouseListeners for seamless button clicks and dynamic table updates.

---

## How to Run the Application

### Prerequisites
* **Java Development Kit (JDK 8 or higher)** installed on your machine.
* A Java-compatible IDE (such as IntelliJ IDEA, Eclipse, or NetBeans) or command-line terminal.

### Compilation and Execution via Terminal

1. Clone or download the project files into a directory.
2. Navigate to the source folder via your terminal.
3. Compile the Java files:
   ```bash
   javac *.java
   ```
4. Run the application:
   ```bash
   java Main
   ```

---

## Project Structure (Single-File / Modular Layout)

The core application encompasses:
* **`MainFrame.java`**: The main Java Swing window orchestrating input tables, control buttons, and output metric panels.
* **`Process.java`**: Data class representing an individual CPU process.
* **`SRTFScheduler.java`**: Core simulation logic for the Shortest Remaining Time First algorithm.
* **`RRScheduler.java`**: Core simulation logic for the Round Robin algorithm featuring queue-based time quantum rotations.