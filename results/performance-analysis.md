Overall Performance Analysis
1. Introduction
This experiment compares the performance of two virtualization approaches:
- Type-1 Hypervisor: Proxmox VE
- Type-2 Hypervisor: VMware Workstation
The comparison is based on system configuration and Sysbench benchmark results.
2. Type-1 Hypervisor - Proxmox
System Configuration
- Guest OS: Ubuntu
- CPU Cores: 2 vCPU
- RAM: 2 GB
- Storage: 20 GB
Sysbench Result
- CPU Score/Result: 1,749.16 events/sec
- Total Events: 17,494
- Execution Time: 10.0005 s
- Average Latency: 0.57 ms
Resource Monitoring
- CPU Usage: Not provided in the submitted screenshots
- Memory Usage: Not provided in the submitted screenshots
3. Type-2 Hypervisor - VMware
System Configuration
- Guest OS: Ubuntu
- CPU Cores: 2 vCPU
- RAM: 2 GB
- Storage: 20 GB
Sysbench Result
- CPU Score/Result: 1,059.10 events/sec
- Total Events: 10,596
- Execution Time: 10.0025 s
- Average Latency: 0.94 ms
Resource Monitoring
- CPU Usage: Not provided in the submitted screenshots
- Memory Usage: Not provided in the submitted screenshots
4. Performance Comparison
CPU Performance
Proxmox Result: 1,749.16 events/sec
VMware Result: 1,059.10 events/sec
Observation: Proxmox VE recorded 1,749.16 events/sec, while VMware Workstation recorded 1,059.10 events/sec in the submitted Sysbench CPU benchmark.
Memory Performance
Proxmox Result: Not provided in the submitted screenshots
VMware Result: Not provided in the submitted screenshots
Observation: Memory benchmark values were not present in the submitted screenshots, so no memory-performance values have been assumed.
Execution Time
Proxmox: 10.0005 s
VMware: 10.0025 s
Observation: Both benchmark runs completed in approximately 10 seconds, with very close execution times.
5. Overall Observation
The experiment was conducted using Ubuntu guest operating systems with the same listed virtual machine resources: 2 vCPU, 2 GB RAM, and 20 GB storage.
The measured Sysbench CPU results were:
- Proxmox VE: 17,494 total events and 1,749.16 events/sec.
- VMware Workstation: 10,596 total events and 1,059.10 events/sec.
- Proxmox VE average latency: 0.57 ms.
- VMware Workstation average latency: 0.94 ms.
- Proxmox VE execution time: 10.0005 s.
- VMware Workstation execution time: 10.0025 s.
The submitted screenshots do not contain memory benchmark or CPU/memory resource-monitoring values, so those values have not been assumed.
6. Conclusion
The experiment helped in understanding the practical performance differences between Type-1 and Type-2 hypervisors.
Based on the recorded Sysbench CPU results, Proxmox VE recorded a higher measured event rate and lower average latency than VMware Workstation under the tested configuration. The execution times were nearly identical.
The final comparison is based on the actual benchmark results obtained during the experiment.
