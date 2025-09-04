# Project-IPV6

A simple IPv6 network simulation project using GNS3.

## Overview

This project demonstrates a basic IPv6 network setup with one router and two PCs connected through a switch, all configured with IPv6 addresses in the `2001:1:1:1::/64` subnet.

## Network Topology

```
     R1 (2001:1:1:1::1/64)
            |
         Switch1
         /     \
       /         \
     PC1         PC2
(2001:1:1:1::2) (2001:1:1:1::3)
```

## Components

- **Router (R1)**: Cisco C7200 router with IPv6 routing enabled
  - Interface: FastEthernet0/0
  - IPv6 Address: 2001:1:1:1::1/64
  
- **Switch1**: Ethernet switch connecting all devices
  
- **PC1**: Virtual PC 
  - IPv6 Address: 2001:1:1:1::2/64
  
- **PC2**: Virtual PC
  - IPv6 Address: 2001:1:1:1::3/64

## Requirements

- GNS3 2.2.43 or compatible version
- Cisco C7200 IOS image (c7200-adventerprisek9-mz.124-24.T5.image)
- VPCS (Virtual PC Simulator)

## Files Structure

```
Project-IPV6/
├── Project-IPV6.gns3           # Main GNS3 project file
├── configuration files/         # Device startup configurations
│   ├── PC1_startup.vpc
│   ├── PC2_startup.vpc
│   └── R1_i1_startup-config.cfg
├── project-files/              # GNS3 runtime files
└── *.csv                       # Packet capture files (Wireshark)
```

## Features Demonstrated

- IPv6 address configuration
- IPv6 routing
- ICMPv6 neighbor discovery
- IPv6 connectivity testing (ping)
- Router advertisements

## Usage

1. Open the project in GNS3
2. Start all devices (R1, Switch1, PC1, PC2)
3. The devices will automatically load their IPv6 configurations
4. Test connectivity between PCs using ping commands

## Testing Connectivity

From PC1 or PC2 console:
```
ping 2001:1:1:1::1    # Ping router
ping 2001:1:1:1::2    # Ping PC1
ping 2001:1:1:1::3    # Ping PC2
```

## Packet Captures

The project includes Wireshark packet captures showing:
- IPv6 neighbor discovery process
- ICMPv6 echo requests/replies
- Router advertisements
- CDP (Cisco Discovery Protocol) messages
