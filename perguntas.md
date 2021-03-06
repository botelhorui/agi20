Type of Cloud -IaaS - Infrastructure as a Service

# 1 - Requirements

## Types of Networks:

- LTE
- Physical (Ethernet, copper, fiber)
- Wireless (Wi-Fi)

## Non-Functional Requirements

- High **security** for transactions and security system
- High **availability** for airport - plane communications and security system
- Medium **latency** (for voice services)

## Datacenter

- Servers: 
	- storage (info about flights and tickets, internal statistics)
	- processing (security, systems health monitoring, load balancing)

- High bandwidth
- Routers, firewalls, switches


# 6 - Tools for managing the infrastructure

## 6.1 - Application/Systems Automation

Vagrant
Docker
Puppet

## 6.2 - Monitoring of Performance

$ iostat, sar, top, etc - *NIX commands to monitor CPU, IO, networking, etc.

Cacti - network graphing tool with GUI



## 6.3 - Faults and Problem Handling

## 6.4 - Configuration Management

Version Control System: git + GitLab

Use a version control system to share configuration files used by vagrant, puppet, gradle, etc. Sharing only config files is benefitial, because they are:

	- much smaller than binary files such as VM snapshots
	- easier to manage with a VCS, unlike binary files

Git specifically because it's solid and widely used.

Gitlab because it provides aditional features, such as workflow management and git hooks. It can be self-hosted, which is best for handling sensitive documents or programs.


## 6.5 - Data Center Infrastructure Management

OpenStack - platform for cloud computing
	- integrates well with vagrant, docker and puppet

TODO:
Ver significado de:
	COBIT
	SDN - Software Defined Networking
