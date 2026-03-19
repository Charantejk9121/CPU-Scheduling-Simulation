[README_cpu_scheduling.md](https://github.com/user-attachments/files/26116543/README_cpu_scheduling.md)
# ⚙️ CPU Scheduling Simulation

> A simulation of classic CPU scheduling algorithms — visualising process execution, calculating performance metrics like waiting time, turnaround time, and CPU utilisation.

[![Language](https://img.shields.io/badge/Language-C%20%2F%20C%2B%2B%20%2F%20Python-blue?style=flat-square)](#tech-stack)
[![OS Concepts](https://img.shields.io/badge/Topic-Operating%20Systems-orange?style=flat-square)](#algorithms-implemented)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](#license)

---

## 📌 Overview

This project simulates fundamental **CPU Scheduling Algorithms** as taught in Operating Systems courses. It models how an OS scheduler manages processes — deciding which process runs next based on the chosen algorithm — and computes key performance metrics to compare scheduling strategies.

---

## 🎯 Objectives

- Implement and simulate classic CPU scheduling algorithms
- Calculate **Waiting Time, Turnaround Time, and CPU Utilisation** for each algorithm
- Visualise scheduling order via **Gantt Charts**
- Compare algorithm performance under different process workloads
- Understand the trade-offs between preemptive and non-preemptive approaches

---

## ⚙️ Algorithms Implemented

| Algorithm | Type | Description |
|-----------|------|-------------|
| **FCFS** (First Come First Serve) | Non-preemptive | Processes are executed in arrival order |
| **SJF** (Shortest Job First) | Non-preemptive | Process with shortest burst time runs next |
| **SRTF** (Shortest Remaining Time First) | Preemptive | Preempts current process if a shorter job arrives |
| **Round Robin (RR)** | Preemptive | Each process gets a fixed time quantum in rotation |
| **Priority Scheduling** | Both | Processes run based on assigned priority value |

---

## 📂 Repository Structure

```
CPU-Scheduling-Simulation/
├── fcfs.py / fcfs.c          # First Come First Serve implementation
├── sjf.py / sjf.c            # Shortest Job First implementation
├── srtf.py / srtf.c          # Shortest Remaining Time First
├── round_robin.py / rr.c     # Round Robin with configurable quantum
├── priority.py               # Priority Scheduling
├── main.py / main.c          # Entry point — run all algorithms
├── gantt.py                  # Gantt chart visualisation (if applicable)
└── README.md                 # Project documentation
```

---

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x / C | Core algorithm implementation |
| Matplotlib (Python) | Gantt chart and performance graph visualisation |
| Pandas (Python) | Process table display and metric calculation |

---

## 📊 Performance Metrics Calculated

| Metric | Description |
|--------|-------------|
| **Arrival Time (AT)** | When a process enters the ready queue |
| **Burst Time (BT)** | CPU time required by the process |
| **Completion Time (CT)** | When a process finishes execution |
| **Turnaround Time (TAT)** | CT − AT (total time from arrival to completion) |
| **Waiting Time (WT)** | TAT − BT (time spent waiting in the ready queue) |
| **Response Time (RT)** | Time from arrival to first CPU allocation |
| **CPU Utilisation** | Percentage of time the CPU is actively running processes |
| **Throughput** | Number of processes completed per unit time |

---

## 🚀 Getting Started

### Prerequisites (Python)

```bash
pip install pandas matplotlib
```

### Run the Simulation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Charantejk9121/CPU-Scheduling-Simulation.git
   cd CPU-Scheduling-Simulation
   ```

2. **Run the main simulation:**
   ```bash
   python main.py
   ```

3. **Or run a specific algorithm:**
   ```bash
   python fcfs.py
   python round_robin.py
   ```

### Sample Input Format

```
Enter number of processes: 4
Process 1 — Arrival Time: 0, Burst Time: 5
Process 2 — Arrival Time: 1, Burst Time: 3
Process 3 — Arrival Time: 2, Burst Time: 8
Process 4 — Arrival Time: 3, Burst Time: 2
Time Quantum (for Round Robin): 2
```

### Sample Output

```
=== FCFS Scheduling ===
Process  AT   BT   CT   TAT  WT
P1        0    5    5    5    0
P2        1    3    8    7    4
P3        2    8   16   14    6
P4        3    2   18   15   13

Average Waiting Time     : 5.75 ms
Average Turnaround Time  : 10.25 ms
CPU Utilisation          : 100%
```

---

## 📈 Gantt Chart (Example)

```
FCFS:
| P1  | P2  | P3          | P4  |
0     5     8            16    18
```

---

## 🔄 Algorithm Comparison

| Algorithm | Avg Waiting Time | Starvation Risk | Preemptive | Best For |
|-----------|-----------------|-----------------|------------|----------|
| FCFS | High | No | No | Simple batch systems |
| SJF | Low | Yes (long jobs) | No | Minimising avg wait time |
| SRTF | Lowest | Yes | Yes | Interactive systems |
| Round Robin | Medium | No | Yes | Time-sharing systems |
| Priority | Varies | Yes (low priority) | Both | Real-time systems |

---

## 💡 Key Concepts

- **Preemption** — The OS can interrupt a running process to give CPU to another
- **Context Switch** — Saving and restoring process state when switching
- **Starvation** — Low-priority processes may never run (solved by aging)
- **Time Quantum** — The fixed time slice used in Round Robin scheduling

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">
  ⚙️ <strong>CPU Scheduling Simulation</strong> — Understanding how your OS decides what runs next.
</p>
