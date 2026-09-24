# CC-Experiment-01: Hypervisor Analysis

## Performance Analysis of Type-1 and Type-2 Hypervisors

This experiment presents a comparative analysis of two virtualization approaches:

* **Type-1 Hypervisor:** Proxmox VE
* **Type-2 Hypervisor:** VMware Workstation

Both hypervisors were used to run an Ubuntu virtual machine, and their performance was evaluated using CPU benchmarking and resource utilization observations.

---

## 1. Objectives

The objectives of this experiment are:

* To understand Type-1 and Type-2 hypervisors.
* To configure and run an Ubuntu virtual machine using Proxmox VE.
* To configure and run an Ubuntu virtual machine using VMware Workstation.
* To perform CPU benchmarking using Sysbench.
* To monitor resource utilization.
* To compare the performance of Type-1 and Type-2 virtualization.

---

## 2. Hypervisor Types

### Type-1 Hypervisor – Proxmox VE

Proxmox VE is a **Type-1 bare-metal hypervisor** that runs directly on the physical hardware.

It provides:

* Direct access to hardware resources
* Virtual machine management
* Efficient resource allocation
* Web-based administration
* Support for server and data-center virtualization

### Type-2 Hypervisor – VMware Workstation

VMware Workstation is a **Type-2 hosted hypervisor** that runs on top of a host operating system.

It provides:

* Easy virtual machine creation
* Desktop-based VM management
* Support for multiple guest operating systems
* Convenient development and testing environment

---

## 3. Experimental Setup

| Parameter       | Proxmox VE   | VMware Workstation |
| --------------- | ------------ | ------------------ |
| Hypervisor Type | Type-1       | Type-2             |
| Guest OS        | Ubuntu       | Ubuntu             |
| CPU Allocation  | 2 vCPU       | 2 vCPU             |
| RAM             | 2 GB         | 2 GB               |
| Storage         | 20 GB        | 20 GB              |
| Benchmark       | Sysbench CPU | Sysbench CPU       |

---

## 4. Experimental Procedure

### Proxmox VE

1. Installed and configured Proxmox VE.
2. Created an Ubuntu virtual machine.
3. Allocated CPU, RAM and storage.
4. Started the virtual machine.
5. Installed Sysbench.
6. Executed the CPU benchmark.
7. Recorded the benchmark results.
8. Monitored resource utilization.

### VMware Workstation

1. Installed VMware Workstation.
2. Created an Ubuntu virtual machine.
3. Allocated CPU, RAM and storage.
4. Started the virtual machine.
5. Installed Sysbench.
6. Executed the CPU benchmark.
7. Recorded the benchmark results.
8. Compared the results with Proxmox VE.

---

## 5. Benchmarking

CPU performance was measured using **Sysbench**.

The following command was used:

```bash
sysbench cpu --cpu-max-prime=20000 run
```

The benchmark results were used for the performance comparison between Proxmox VE and VMware Workstation.

---

## 6. Experimental Screenshots

Only **one representative screenshot from each hypervisor** is included in this README.

### Proxmox VE

![Proxmox VE Sysbench Result](screenshots/type1-proxmox/06-proxmox-sysbench-result.png)

### VMware Workstation

![VMware Workstation Sysbench Result](screenshots/type2-vmware/04-vmware-sysbench-result.png)

---

# 7. Performance Comparison

The following graphs provide a visual comparison between Proxmox VE and VMware Workstation based on the experimental results.

## 7.1 CPU Performance Comparison

![CPU Performance Comparison](screenshots/comparison/01-cpu-performance-comparison.png)

This graph compares the CPU benchmark performance obtained from the two virtualization environments using Sysbench.

---

## 7.2 Resource Utilization Comparison

![Resource Utilization Comparison](screenshots/comparison/02-resource-utilization-comparison.png)

This graph compares the observed resource utilization of the virtual machines during the experiment.

---

## 7.3 Overall Performance Comparison

![Overall Performance Comparison](screenshots/comparison/03-overall-performance-comparison.png)

This graph provides an overall visual comparison of the performance measurements obtained from Proxmox VE and VMware Workstation.

---

## 8. Performance Analysis

The detailed numerical results, observations and analysis are available in:

**[Performance Analysis](results/performance-analysis.md)**

The analysis contains the experimental results obtained from the Proxmox VE and VMware Workstation environments.

---

## 9. Type-1 vs Type-2 Comparison

| Feature                 | Proxmox VE                | VMware Workstation          |
| ----------------------- | ------------------------- | --------------------------- |
| Hypervisor Type         | Type-1                    | Type-2                      |
| Runs On                 | Physical hardware         | Host operating system       |
| Hardware Access         | Direct                    | Through host OS             |
| Primary Usage           | Server / Data Center      | Desktop / Development       |
| Management              | Web-based                 | Desktop application         |
| Virtualization Overhead | Lower                     | Higher due to host OS layer |
| Typical Use             | Production virtualization | Testing and development     |

---

## 10. Key Observations

* Proxmox VE operates directly on physical hardware as a Type-1 hypervisor.
* VMware Workstation operates above the host operating system as a Type-2 hypervisor.
* Both environments successfully supported the Ubuntu guest operating system.
* Sysbench was used to evaluate CPU performance.
* Resource utilization was monitored during the experiment.
* Graphical comparisons make it easier to observe differences between the two virtualization approaches.
* Detailed experimental results are provided in the performance analysis document.

---

## 11. Repository Structure

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
│       ├── 01-cpu-performance-comparison.png
│       ├── 02-resource-utilization-comparison.png
│       └── 03-overall-performance-comparison.png
│
├── results/
│   └── performance-analysis.md
│
└── README.md
```

---

## 12. Conclusion

This experiment provided practical experience with both Type-1 and Type-2 virtualization.

Proxmox VE was studied as a bare-metal hypervisor, while VMware Workstation was studied as a hosted hypervisor. Ubuntu virtual machines were configured in both environments and evaluated using Sysbench.

The benchmark results, resource utilization observations and graphical comparisons provide a practical understanding of the performance characteristics of the two virtualization approaches.
