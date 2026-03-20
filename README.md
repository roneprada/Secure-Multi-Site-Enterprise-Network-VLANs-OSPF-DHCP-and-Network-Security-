# Secure-Multi-Site-Enterprise-Network-VLANs-OSPF-DHCP-and-Network-Security-
Designed a secure multi-site network using VLANs, OSPF, DHCP, and Layer 2 security features (ACLs, DHCP Snooping, DAI, Port Security).
# Enterprise Network Lab -- VLANs, Routing, and Security

## Overview

In this lab I built a multi-site network using a core router, multiple
distribution routers, and access switches. The goal was to understand
how VLANs, routing, DHCP, and network security work together in a real
environment.

## Network Design

-   Core router connected to 3 distribution routers\
-   Each distribution router connected to its own switch\
-   Switches are not connected to each other\
-   VLANs are implemented across all switches

### VLANs used:

-   VLAN 10\
-   VLAN 20\
-   VLAN 30

Each VLAN has its own subnet and gateway configured on the router using
subinterfaces.

## Inter-VLAN Routing

Configured router-on-a-stick on all distribution routers.

## DHCP Configuration

-   Created DHCP pools for each VLAN\
-   Used correct default gateway with default-router\
-   Excluded important IP addresses\
-   Configured ip helper-address for DHCP across VLANs

## OSPF Routing

-   Enabled OSPF for communication between routers\
-   Advertised all VLAN networks\
-   Set loopback interface as passive

## Security Configuration

### DHCP Snooping

-   Enabled on VLAN 10, 20, 30\
-   Trusted uplink ports only

### Dynamic ARP Inspection (DAI)

-   Enabled on VLAN 10, 20, 30\
-   Protects against ARP spoofing

### Port Security

-   Maximum 1 MAC per port\
-   Sticky MAC\
-   Violation shutdown

### ACL (VLAN Isolation)

-   Blocked communication between VLANs\
-   Each VLAN can only communicate within itself

## Switch Configuration

-   Created VLANs on all switches\
-   Assigned access ports\
-   Configured trunk links\
-   Configured SVI for management

## What I Learned

-   VLAN segmentation in real networks\
-   Inter-VLAN routing with subinterfaces\
-   DHCP relay using helper-address\
-   Difference between Layer 2 and Layer 3\
-   Network security implementation

## Skills Demonstrated

-   VLAN configuration\
-   Routing (OSPF)\
-   DHCP\
-   Network security (ACL, DAI, DHCP Snooping, Port Security)\
-   Troubleshooting
