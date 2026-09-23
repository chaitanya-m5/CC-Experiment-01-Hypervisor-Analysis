# Overall Performance Analysis

## 1. Introduction

This experiment compares the performance of two virtualization approaches:

- **Type-1 Hypervisor:** Proxmox VE
- **Type-2 Hypervisor:** VMware Workstation

The comparison is based on the virtual machine configuration, Sysbench CPU benchmark results, and resource monitoring information obtained during the experiment.

> **Note:** Memory benchmark performance is excluded from this analysis because a dedicated memory benchmark result was not provided.

---

## 2. Type-1 Hypervisor – Proxmox VE

### 2.1 System Configuration

| Parameter | Proxmox VE |
|---|---|
| Hypervisor Type | Type-1 |
| Guest OS | Ubuntu |
| CPU Cores | 2 vCPU |
| RAM | 2 GB |
| Storage | 20 GB |

### 2.2 Sysbench CPU Result

| Parameter | Result |
|---|---:|
| Events per Second | **1,749.16 events/sec** |
| Total Events | **17,494** |
| Execution Time | **10.0005 s** |
| Average Latency | **0.57 ms** |

### 2.3 Resource Monitoring

The Proxmox VM monitoring screenshot shows:

- **CPU Usage:** 0.75%
- **Memory Usage:** 88.12% (1.76 GiB / 2.00 GiB)

---

## 3. Type-2 Hypervisor – VMware Workstation

### 3.1 System Configuration

| Parameter | VMware Workstation |
|---|---|
| Hypervisor Type | Type-2 |
| Guest OS | Ubuntu |
| CPU Cores | 2 vCPU |
| RAM | 2 GB |
| Storage | 20 GB |

### 3.2 Sysbench CPU Result

| Parameter | Result |
|---|---:|
| Events per Second | **1,059.10 events/sec** |
| Total Events | **10,596** |
| Execution Time | **10.0025 s** |
| Average Latency | **0.94 ms** |

### 3.3 Resource Monitoring

The submitted VMware screenshots provide system and VM configuration information, but a dedicated VMware resource-monitoring screenshot with CPU and memory usage values was not provided.

Therefore, VMware resource-monitoring values are **not included or assumed** in this analysis.

---

## 4. Performance Comparison

### 4.1 CPU Performance

| Parameter | Type-1: Proxmox VE | Type-2: VMware Workstation |
|---|---:|---:|
| Total Events | **17,494** | **10,596** |
| Events per Second | **1,749.16** | **1,059.10** |
| Average Latency | **0.57 ms** | **0.94 ms** |
| Execution Time | **10.0005 s** | **10.0025 s** |

### Observation

The Sysbench CPU benchmark recorded:

- Proxmox VE: **1,749.16 events/sec**
- VMware Workstation: **1,059.10 events/sec**

The measured average latency was:

- Proxmox VE: **0.57 ms**
- VMware Workstation: **0.94 ms**

The execution times were very close:

- Proxmox VE: **10.0005 s**
- VMware Workstation: **10.0025 s**

---

## 5. Resource Usage Comparison

| Resource | Proxmox VE | VMware Workstation |
|---|---:|---:|
| CPU Usage | **0.75%** | Not provided |
| Memory Usage | **88.12% (1.76 GiB / 2.00 GiB)** | Not provided |

The Proxmox VM monitoring screenshot provides CPU and memory usage values. A corresponding VMware resource-monitoring screenshot was not included, so VMware values are not assumed.

---

## 6. Overall Observation

The experiment was conducted using Ubuntu guest operating systems with the same virtual machine resources:

- **2 vCPU**
- **2 GB RAM**
- **20 GB storage**

The measured Sysbench CPU results were:

- **Proxmox VE:** 17,494 total events and 1,749.16 events/sec
- **VMware Workstation:** 10,596 total events and 1,059.10 events/sec

The measured average latency was:

- **Proxmox VE:** 0.57 ms
- **VMware Workstation:** 0.94 ms

The execution time was approximately 10 seconds for both benchmark runs.

The Proxmox VM resource monitoring showed **0.75% CPU usage** and **88.12% memory usage (1.76 GiB / 2.00 GiB)** at the time of the captured monitoring result.

Memory benchmark performance has been excluded because dedicated Sysbench memory benchmark results were not provided.

---

## 7. Conclusion

The experiment provided a practical comparison between a Type-1 hypervisor, Proxmox VE, and a Type-2 hypervisor, VMware Workstation.

Based on the recorded Sysbench CPU benchmark:

- Proxmox VE recorded **1,749.16 events/sec**.
- VMware Workstation recorded **1,059.10 events/sec**.
- Proxmox VE recorded an average latency of **0.57 ms**.
- VMware Workstation recorded an average latency of **0.94 ms**.
- Both executions completed in approximately **10 seconds**.

The comparison is based on the actual benchmark and monitoring values available from the submitted screenshots. Memory benchmark performance has intentionally been excluded.
