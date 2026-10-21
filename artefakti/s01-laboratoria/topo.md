# Laboratory Environment: S01 Topology & Configuration

## Overview & Hypervisor Specs
This infrastructure is hosted locally using **Oracle VM VirtualBox** and comprises two Ubuntu (64-bit) nodes connected via virtual internal networks.

### Virtual Machine Profiles
* **`gw` (Gateway Node)**
  * **vCPUs:** 2 processors[cite: 2]
  * **Memory:** 3000 MiB RAM[cite: 2]
  * **Interfaces:** NAT (`enp0s3`), LAN1 (`enp0s8`), LAN2 (`enp0s9`)[cite: 2]
* **`srv` (Internal Server Node)**
  * **vCPUs:** 2 processors[cite: 3]
  * **Memory:** 2048 MiB RAM[cite: 3]
  * **Interfaces:** LAN1 (`enp0s3`)[cite: 3]


## Network Topology Diagram

```text
       [ External WAN / Internet ]
                   |
            (NAT / DHCP)
                   |
         +-------------------+
         |    gw (Ubuntu)    |
         |  2 vCPU / 3000MB  |
         +-------------------+
            /             \
  (LAN1)   /               \   (LAN2 - Reserved)
192.168.1.1/24           192.168.2.1/24
          /
         v
+-------------------+
|    srv (Ubuntu)   |
|  2 vCPU / 2048MB  |
|  192.168.1.2/24   |
+-------------------+
