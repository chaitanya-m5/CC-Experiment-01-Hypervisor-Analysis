# CC-Experiment-01: Hypervisor Analysis

## Performance Analysis of Type-1 and Type-2 Hypervisors

---

## 1. Introduction

This experiment analyzes and compares two virtualization approaches:

* **Type-1 Hypervisor:** Proxmox VE
* **Type-2 Hypervisor:** VMware Workstation

Ubuntu Virtual Machines were deployed in both environments with comparable configurations. CPU performance was evaluated using the **Sysbench CPU benchmark**, while system configuration and resource utilization were also observed.

The experimental results are presented using comparison graphs.

---

## 2. Objectives

* Understand Type-1 and Type-2 hypervisor architectures.
* Deploy Ubuntu Virtual Machines using Proxmox VE and VMware Workstation.
* Configure comparable resources for both virtual machines.
* Perform CPU benchmarking using Sysbench.
* Observe system and resource utilization.
* Compare virtualization performance.
* Represent the experimental results using graphs.

---

# 3. Hypervisor Architecture

## 3.1 Type-1 Hypervisor – Proxmox VE

Proxmox VE is a Type-1 or bare-metal hypervisor platform that operates directly on the physical hardware.

```text
+--------------------------------------+
|        Ubuntu Virtual Machine        |
|          Sysbench Benchmark          |
+--------------------------------------+
|          Proxmox VE / KVM            |
|          Type-1 Hypervisor           |
+--------------------------------------+
|          Physical Hardware           |
|       CPU | RAM | Storage | NIC      |
+--------------------------------------+
```

---

## 3.2 Type-2 Hypervisor – VMware Workstation

VMware Workstation is a Type-2 or hosted hypervisor that operates on top of a host operating system.

```text
+--------------------------------------+
|        Ubuntu Virtual Machine        |
|          Sysbench Benchmark          |
+--------------------------------------+
|        VMware Workstation            |
|          Type-2 Hypervisor           |
+--------------------------------------+
|        Host Operating System         |
|              Windows                 |
+--------------------------------------+
|          Physical Hardware           |
|       CPU | RAM | Storage | NIC      |
+--------------------------------------+
```

---

# 4. Experimental Setup

Comparable resources were allocated to the Ubuntu virtual machines.

| Parameter       | Proxmox VE   | VMware Workstation |
| --------------- | ------------ | ------------------ |
| Hypervisor Type | Type-1       | Type-2             |
| Guest OS        | Ubuntu       | Ubuntu             |
| CPU             | 2 vCPU       | 2 vCPU             |
| RAM             | 2 GB         | 2 GB               |
| Storage         | 20 GB        | 20 GB              |
| Benchmark       | Sysbench CPU | Sysbench CPU       |

---

# 5. Experimental Evidence

Only selected screenshots are included here to keep the README concise. The complete set of screenshots is available in the repository.

## Proxmox VE

### Proxmox Dashboard

![Proxmox Dashboard](screenshots/type1-proxmox/01-proxmox-dashboard.png)

### Proxmox VM Configuration

![Proxmox VM Configuration](screenshots/type1-proxmox/02-proxmox-vm-configuration.png)

### Proxmox Sysbench Result

![Proxmox Sysbench Result](screenshots/type1-proxmox/06-proxmox-sysbench-result.png)

---

## VMware Workstation

### VMware VM Configuration

![VMware VM Configuration](screenshots/type2-vmware/01-vmware-vm-configuration.png)

### VMware Sysbench Result

![VMware Sysbench Result](screenshots/type2-vmware/04-vmware-sysbench-result.png)

---

# 6. Benchmarking

The **Sysbench CPU benchmark** was used to evaluate CPU performance inside both Ubuntu virtual machines.

The benchmark was executed using the same workload in both environments.

```bash
sysbench cpu --cpu-max-prime=20000 run
```

The benchmark provides measurements such as:

* Total execution time
* Number of events
* Events per second
* Average latency
* Maximum latency
* 95th percentile latency

---

# 7. Performance Comparison

The experimental results were compared using graphical analysis.

## 7.1 Overall Hypervisor Performance

![Overall Hypervisor Performance](screenshots/comparison/01-hypervisor-performance-comparison.png)

This graph provides an overall comparison of the measured performance of Proxmox VE and VMware Workstation.

---

## 7.2 CPU Performance Comparison

![CPU Performance Comparison](screenshots/comparison/02-cpu-performance-comparison.png)

This graph compares the CPU benchmark performance obtained from the two virtualization environments.

---

## 7.3 Resource Utilization Comparison

![Resource Utilization Comparison](screenshots/comparison/03-resource-utilization-comparison.png)

This graph compares the observed resource utilization of the virtual machines.

---

## 7.4 Latency Comparison

![Latency Comparison](screenshots/comparison/04-latency-comparison.png)

This graph compares the latency-related measurements obtained from the Sysbench benchmark.

---

# 8. Performance Analysis

The detailed numerical results, observations, tables, and analysis are provided separately in:

**[Performance Analysis](results/performance-analysis.md)**

The performance analysis contains the complete experimental results without making the main README unnecessarily lengthy.

---

# 9. Type-1 vs Type-2 Comparison

| Feature            | Proxmox VE                             | VMware Workstation              |
| ------------------ | -------------------------------------- | ------------------------------- |
| Hypervisor Type    | Type-1                                 | Type-2                          |
| Architecture       | Bare-metal                             | Hosted                          |
| Host OS Layer      | No separate desktop OS layer           | Required                        |
| Guest OS           | Ubuntu                                 | Ubuntu                          |
| CPU Allocation     | 2 vCPU                                 | 2 vCPU                          |
| RAM Allocation     | 2 GB                                   | 2 GB                            |
| Storage Allocation | 20 GB                                  | 20 GB                           |
| Benchmark          | Sysbench CPU                           | Sysbench CPU                    |
| Management         | Web interface                          | Desktop application             |
| Typical Use        | Server / infrastructure virtualization | Desktop / development / testing |

---

# 10. Resource Utilization

Resource utilization was observed during virtual machine execution.

The experiment considered:

* CPU utilization
* Memory utilization
* System load
* Virtual machine resource consumption

The detailed resource-monitoring evidence is available in:

```text
screenshots/type1-proxmox/07-proxmox-resource-monitoring.png
```

The complete analysis is documented in `results/performance-analysis.md`.

---

# 11. Key Observations

1. Ubuntu was successfully deployed in both virtualization environments.
2. Comparable VM configurations were used for the experiment.
3. Sysbench was used with the same CPU workload.
4. Proxmox VE demonstrated a Type-1 hypervisor architecture.
5. VMware Workstation demonstrated a Type-2 hypervisor architecture.
6. Resource utilization was monitored during execution.
7. Graphical analysis was used to compare the experimental results.
8. Hypervisor architecture, host-system activity, and VM configuration can affect measured performance.

---

# 12. Conclusion

This experiment provided practical understanding of Type-1 and Type-2 virtualization.

Proxmox VE was evaluated as a Type-1 hypervisor, while VMware Workstation was evaluated as a Type-2 hypervisor. Comparable Ubuntu virtual machines were deployed and benchmarked using Sysbench.

The experiment included system configuration verification, resource monitoring, CPU benchmarking, and graphical performance comparison.

The complete screenshots and detailed numerical analysis are maintained in the repository, while the most relevant evidence and comparison graphs are presented in this README.

---

# 13. Repository Structure

```text
CC-Experiment-01-Hypervisor-Analysis/
│
├── screenshots/
│   │
│   ├── type1-proxmox/
│   │   ├── 01-proxmox-dashboard.png
│   │   ├── 02-proxmox-vm-configuration.png
│   │   ├── 03-proxmox-vm-running.png
│   │   ├── 04-proxmox-ubuntu-console.png
│   │   ├── 05-proxmox-system-configuration.png
│   │   ├── 06-proxmox-sysbench-result.png
│   │   └── 07-proxmox-resource-monitoring.png
│   │
│   ├── type2-vmware/
│   │   ├── 01-vmware-vm-configuration.png
│   │   ├── 02-vmware-vm-running.png
│   │   ├── 03-vmware-system-configuration.png
│   │   └── 04-vmware-sysbench-result.png
│   │
│   └── comparison/
│       ├── 01-hypervisor-performance-comparison.png
│       ├── 02-cpu-performance-comparison.png
│       ├── 03-resource-utilization-comparison.png
│       └── 04-latency-comparison.png
│
├── results/
│   └── performance-analysis.md
│
└── README.md
```

---

# 14. Experiment Deliverables

| Deliverable        | Location                          |
| ------------------ | --------------------------------- |
| Proxmox Evidence   | `screenshots/type1-proxmox/`      |
| VMware Evidence    | `screenshots/type2-vmware/`       |
| Comparison Graphs  | `screenshots/comparison/`         |
| Detailed Results   | `results/performance-analysis.md` |
| Main Documentation | `README.md`                       |

---

## CC Experiment 01 – Hypervisor Analysis

**Cloud Computing**

**Type-1 vs Type-2 Hypervisor Performance Analysis**
