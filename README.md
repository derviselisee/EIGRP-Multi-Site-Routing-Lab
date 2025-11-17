# EIGRP-Multi-Site-Routing-Lab

EIGRP Multi-Site Routing Lab
Implementation Summary

This project builds a three-router EIGRP network that connects three separate LANs through point-to-point WAN links.
Each router was assigned LAN and WAN interfaces, configured with proper IP addressing, and enrolled into EIGRP AS 100.
EIGRP neighbor adjacencies were formed between R1–R2 and R2–R3, and full end-to-end connectivity was validated across all networks.

Below is the complete implementation workflow, following the exact order of your screenshots.

1. Router R1 Configuration
Interface Configuration

• Configured g0/0 for the WAN link to Router2 (10.10.0.1/30).
• Configured g3/0 for the LAN network (192.168.10.254/24).
• Enabled interfaces with no shutdown.
• Verified interface status with show ip int.

EIGRP Setup

• Enabled EIGRP AS 100.
• Set router-id to 1.1.1.1.
• Advertised LAN network 192.168.10.0/24.
• Advertised WAN network 10.10.0.0/30.
• Disabled auto-summary.
• Set passive interface on LAN.
• Verified neighbors and routing table using:

show ip eigrp neighbors

show ip eigrp topology

2. Router R2 Configuration
Interface Configuration

• Configured LAN interface g3/0 with 192.168.20.254/24.
• Configured WAN g0/0 to R1 (10.10.0.2/30).
• Configured WAN g1/0 to R3 (20.20.0.1/30).
• Added bandwidth and delay adjustments to simulate real-world metrics.
• Enabled interfaces with no shutdown.
• Verified IP assignments and link status.

EIGRP Setup

• Enabled EIGRP AS 100 with router-id 2.2.2.2.
• Advertised WAN networks to R1 and R3.
• Advertised LAN network 192.168.20.0/24.
• Disabled auto-summary.
• Set LAN as passive interface.
• Verified adjacencies with both R1 and R3.
• Confirmed successful topology entries for all networks.

3. Router R3 Configuration
Interface Configuration

• Configured WAN interface g1/0 to connect to R2 (20.20.0.2/30).
• Configured LAN interface g3/0 with 192.168.30.254/24.
• Activated interfaces with no shutdown.
• Verified connectivity with ICMP tests to R2.

EIGRP Setup

• Enabled EIGRP AS 100 with router-id 3.3.3.3.
• Advertised 192.168.30.0/24.
• Advertised WAN network 20.20.0.0/30.
• Disabled auto-summary.
• Set LAN as passive.
• Verified neighbor adjacency with R2.
• Checked routing information with:

show ip eigrp neighbor

show ip eigrp topology

4. End-to-End Connectivity Validation
From Router R1

• Successfully pinged R3 LAN gateway at 192.168.30.254.
• Verified full path R1 → R2 → R3.

From Router R3

• Successfully pinged R1 LAN gateway at 192.168.10.254.
• Verified consistent routing latency and stable adjacency.

All three LANs achieved full reachability, proving correct EIGRP route propagation and adjacency formation.

Skills Demonstrated

• EIGRP routing configuration on multi-router topologies.
• Subnetting and WAN/LAN addressing design.
• Interface configuration, bandwidth tuning, and descriptive documentation.
• Neighbor adjacency verification and troubleshooting.
• EIGRP topology and successor/feasible successor analysis.
• End-to-end routing validation using ICMP and routing tables.
• Applying passive interfaces and auto-summary control.
• Simulating enterprise routing behavior using GNS3.

1
<img width="1645" height="786" alt="Topolgy" src="https://github.com/user-attachments/assets/53f70d09-815a-4ef0-9eb1-08589b43b4a3" />
