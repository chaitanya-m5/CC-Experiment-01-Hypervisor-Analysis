Hypervisor Performance Comparison
1. Virtual Machine Configuration
Parameter	Type-1: Proxmox VE	Type-2: VMware Workstation
Hypervisor Type	Type-1	Type-2
Guest OS	Ubuntu	Ubuntu
CPU	2 vCPU	2 vCPU
Memory	2 GB	2 GB
Disk	20 GB	20 GB


2. CPU Benchmark Results
Benchmark: Sysbench CPU
Prime Number Limit: 20,000
Number of Threads: 1
Benchmark Parameter	Type-1: Proxmox VE	Type-2: VMware Workstation
Total Execution Time	10.0005 s	10.0025 s
Total Events	17,494	10,596
Events per Second	1,749.16	1,059.10
Average Latency	0.57 ms	0.94 ms


3. Overall Result
The same Sysbench CPU benchmark was executed on both hypervisors using the same virtual machine configuration.
- Proxmox VE: 17,494 total events and 1,749.16 events per second.
- VMware Workstation: 10,596 total events and 1,059.10 events per second.
- Execution time: Approximately 10 seconds for both hypervisors.
- Average latency: 0.57 ms for Proxmox VE and 0.94 ms for VMware Workstation.
Conclusion
Under the tested configuration, Proxmox VE recorded higher CPU benchmark throughput and lower average latency than VMware Workstation. The execution times were almost identical.
These results are specific to the tested hardware, virtual machine configuration, Sysbench version, and benchmark settings.
4. Screenshot Reference
Screenshot	File Name
Proxmox VE Sysbench Result	06-proxmox-sysbench-result.png
VMware Workstation Sysbench Result	04-vmware-sysbench-result.png
Final Performance Comparison	01-hypervisor-performance-comparison.png
