# Hypervisor Performance Comparison

## 1. Overview

This experiment compares the performance of two virtualization approaches:

- **Type-1 Hypervisor:** Proxmox VE
- **Type-2 Hypervisor:** VMware Workstation

Both virtual machines were configured with the same basic resources and tested using the **Sysbench CPU benchmark**.

The comparison focuses on:

- Total execution time
- Total number of events
- Events per second
- Average latency

> **Note:** Memory benchmark performance is not included because a dedicated Sysbench memory benchmark result was not obtained.

---

## 2. Virtual Machine Configuration

| Parameter | Type-1 Proxmox VE | Type-2 VMware Workstation |
|---|---|---|
| Hypervisor Type | Type-1 | Type-2 |
| Guest OS | Ubuntu | Ubuntu |
| CPU | 2 vCPU | 2 vCPU |
| Memory | 2 GB | 2 GB |
| Storage | 20 GB | 20 GB |

---

## 3. Sysbench CPU Benchmark Results

| Parameter | Type-1 Proxmox VE | Type-2 VMware Workstation |
|---|---:|---:|
| Total Execution Time | **10.0005 s** | **10.0025 s** |
| Total Events | **17,494** | **10,596** |
| Events per Second | **1,749.16** | **1,059.10** |
| Average Latency | **0.57 ms** | **0.94 ms** |

---

## 4. Performance Comparison

### 4.1 Events per Second

The Sysbench CPU benchmark recorded:

- **Proxmox VE:** 1,749.16 events/sec
- **VMware Workstation:** 1,059.10 events/sec

```mermaid
xychart-beta
    title "Events per Second"
    x-axis ["Proxmox VE", "VMware Workstation"]
    y-axis "Events/sec" 0 --> 2000
    bar [1749.16, 1059.10]
