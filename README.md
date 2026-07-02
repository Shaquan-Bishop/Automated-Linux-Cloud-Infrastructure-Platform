Automated Linux Cloud Infrastructure Platform

A long-term, continuously maintained Red Hat Enterprise Linux (RHEL) infrastructure and automation lab designed to build and reinforce real-world systems administration, DevOps, and cloud engineering skills.

This environment focuses on hands-on experience with enterprise Linux systems, including SELinux, package repositories, storage management, networking, system services, and Ansible automation across a multi-node virtual infrastructure.

🚀 Project Goals

This lab is built for long-term skill development in:

Enterprise Linux system administration (RHEL/CentOS)
Infrastructure automation with Ansible
Virtualized infrastructure design and management
Networking and service deployment
Continuous hands-on practice with production-like systems

The environment is intentionally designed to evolve over time as new technologies, tools, and workloads are introduced.

🖥️ Hardware (Initial Iteration)

The first iteration of the home lab is built on cost-effective, compact hardware:

3x Dell OptiPlex 3070
Intel 8th Gen Core i5 CPUs
16GB RAM per node
2 nodes: 256GB NVMe storage
1 control node: 500GB NVMe + 1TB SSD (NFS storage)
Networking
1x 8-Port Managed Gigabit Switch

This setup was chosen to balance performance, cost, and physical footprint while avoiding the need for a full server rack environment.

💻 Software Stack
Hypervisor: Proxmox VE v9.2-1
Operating Systems:
Red Hat Enterprise Linux 10
CentOS 10

All infrastructure is fully virtualized and managed through Proxmox.

🧱 Infrastructure Layout
Control Node (Bare Metal)
Dedicated primary management node
Runs full allocated hardware resources
Hosts critical management services
Acts as central control point for the entire environment
Node 2 (Application / Services Layer)

Virtual machines hosted:

web1 (Web services)
app1 (Application server)
db1 (Database server)
auth1 (Authentication services)
container1 (Containerized workloads)
Node 3 (Automation / RHEL Targets / Support Systems)

Virtual machines hosted:

rhel1 (Ansible target)
rhel2 (Ansible target)
centos1 (Ansible target)
breakfix1 (system recovery / troubleshooting environment)
monitor1 (monitoring stack)
🧠 Design Decisions

The architecture was intentionally designed based on the following principles:

1. Resource-Based VM Distribution
VMs are split across nodes based on workload requirements to ensure efficient CPU and memory utilization. For example, the monitoring system was moved to Node 3 due to higher available RAM.

2. Cost Optimization
This is an initial-phase build using consumer-grade hardware and open-source software to reduce cost while maintaining enterprise-like functionality. Future upgrades are planned as the lab evolves.

3. Physical Space Efficiency
Dell OptiPlex 3070 systems were selected due to their compact form factor, allowing the entire lab to operate in a small home environment without requiring a server rack.

🎯 Purpose

Currently, this home lab is used for:

Personal hands-on learning
Keeping technical skills current with modern infrastructure tools
Experimenting with Linux systems administration and automation
Future Potential Use Cases:
Personal chatbot hosting environment
Network-wide ad blocking services
Expanded DevOps / cloud simulation platform
🔐 Access & Management
All nodes and VMs are headless
Access is performed remotely via PuTTY (SSH)
Centralized management through the control node
