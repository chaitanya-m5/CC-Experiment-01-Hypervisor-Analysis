[README.md](https://github.com/user-attachments/files/32573875/README.md)
# Overall Performance Analysis

## 1. Introduction

This experiment compares the performance of two virtualization approaches:

- **Type-1 Hypervisor:** Proxmox VE
- **Type-2 Hypervisor:** VMware Workstation

The comparison is based on the virtual machine configuration, Sysbench CPU benchmark results, and resource monitoring information obtained during the experiment.

---

# 2. Type-1 Hypervisor – Proxmox VE

## 2.1 System Configuration

| Parameter | Proxmox VE |
|---|---|
| Hypervisor Type | Type-1 |
| Guest OS | Ubuntu |
| CPU Cores | 2 vCPU |
| RAM | 2 GB |
| Storage | 20 GB |

## 2.2 Sysbench CPU Result

| Parameter | Result |
|---|---:|
| Events per Second | **1,749.16 events/sec** |
| Total Events | **17,494** |
| Execution Time | **10.0005 s** |
| Average Latency | **0.57 ms** |

## 2.3 Resource Monitoring

The Proxmox VM monitoring screenshot shows:

- **CPU Usage:** 0.75%
- **Memory Usage:** 88.12% (1.76 GiB / 2.00 GiB)

### Proxmox CPU Usage

![Proxmox CPU Usage](graphs/05_proxmox_cpu_usage.png)

### Proxmox Memory Usage

![Proxmox Memory Usage](graphs/06_proxmox_memory_usage.png)

---

# 3. Type-2 Hypervisor – VMware Workstation

## 3.1 System Configuration

| Parameter | VMware Workstation |
|---|---|
| Hypervisor Type | Type-2 |
| Guest OS | Ubuntu |
| CPU Cores | 2 vCPU |
| RAM | 2 GB |
| Storage | 20 GB |

## 3.2 Sysbench CPU Result

| Parameter | Result |
|---|---:|
| Events per Second | **1,059.10 events/sec** |
| Total Events | **10,596** |
| Execution Time | **10.0025 s** |
| Average Latency | **0.94 ms** |

## 3.3 Resource Monitoring

A dedicated VMware resource-monitoring screenshot with CPU and memory usage values was not provided. Therefore, VMware resource-monitoring values are not assumed.

---

# 4. Performance Comparison

## 4.1 CPU Performance

| Parameter | Type-1: Proxmox VE | Type-2: VMware Workstation |
|---|---:|---:|
| Total Events | **17,494** | **10,596** |
| Events per Second | **1,749.16** | **1,059.10** |
| Average Latency | **0.57 ms** | **0.94 ms** |
| Execution Time | **10.0005 s** | **10.0025 s** |

## 4.2 Total Execution Time

![Total Execution Time Comparison](graphs/01_execution_time.png)

Proxmox VE: **10.0005 s**  
VMware Workstation: **10.0025 s**

## 4.3 Total Events

![Total Events Comparison](graphs/02_total_events.png)

Proxmox VE: **17,494 events**  
VMware Workstation: **10,596 events**

## 4.4 Events per Second

![Events per Second Comparison](graphs/03_events_per_second.png)

Proxmox VE: **1,749.16 events/sec**  
VMware Workstation: **1,059.10 events/sec**

Difference: **690.06 events/sec**

## 4.5 Average Latency

![Average Latency Comparison](graphs/04_average_latency.png)

Proxmox VE: **0.57 ms**  
VMware Workstation: **0.94 ms**

Difference: **0.37 ms**

---

# 5. Resource Usage Comparison

| Resource | Proxmox VE | VMware Workstation |
|---|---:|---:|
| CPU Usage | **0.75%** | Not provided |
| Memory Usage | **88.12% (1.76 GiB / 2.00 GiB)** | Not provided |

## 5.1 Proxmox CPU Resource Usage

![Proxmox CPU Resource Usage](graphs/05_proxmox_cpu_usage.png)

## 5.2 Proxmox Memory Resource Usage

![Proxmox Memory Resource Usage](graphs/06_proxmox_memory_usage.png)

> VMware CPU and memory resource-usage graphs are not included because corresponding monitoring values were not provided.

---

# 6. Overall Observation

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

The Proxmox VM resource monitoring showed:

- **CPU usage:** 0.75%
- **Memory usage:** 88.12% (1.76 GiB / 2.00 GiB)

Memory benchmark performance has been excluded because dedicated Sysbench memory benchmark results were not provided.

---

# 7. Combined Performance Summary

| Parameter | Type-1 Proxmox VE | Type-2 VMware Workstation |
|---|---:|---:|
| Hypervisor Type | Type-1 | Type-2 |
| Guest OS | Ubuntu | Ubuntu |
| CPU | 2 vCPU | 2 vCPU |
| RAM | 2 GB | 2 GB |
| Storage | 20 GB | 20 GB |
| Total Execution Time | **10.0005 s** | **10.0025 s** |
| Total Events | **17,494** | **10,596** |
| Events per Second | **1,749.16** | **1,059.10** |
| Average Latency | **0.57 ms** | **0.94 ms** |
| CPU Resource Usage | **0.75%** | Not provided |
| Memory Resource Usage | **88.12%** | Not provided |

---

# 8. Conclusion

The experiment provided a practical comparison between a Type-1 hypervisor, Proxmox VE, and a Type-2 hypervisor, VMware Workstation.

Based on the recorded Sysbench CPU benchmark:

- Proxmox VE recorded **1,749.16 events/sec**.
- VMware Workstation recorded **1,059.10 events/sec**.
- Proxmox VE recorded an average latency of **0.57 ms**.
- VMware Workstation recorded an average latency of **0.94 ms**.
- Both executions completed in approximately **10 seconds**.

The Proxmox resource monitoring result recorded **0.75% CPU usage** and **88.12% memory usage (1.76 GiB / 2.00 GiB)** at the time of the captured monitoring result.

The comparison is based on the actual benchmark and monitoring values available from the submitted screenshots. Memory benchmark performance has intentionally been excluded.

---

# 9. Benchmark Command

```bash
sysbench cpu --cpu-max-prime=20000 run
```

The benchmark used a prime-number limit of **20,000**.

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
| CPU Usage | **0.75%** |
| Memory Usage | **88.12% (1.76 GiB / 2.00 GiB)** | 

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

The comparison is based on the actual benchmark and monitoring values available from the submitted screenshots.
