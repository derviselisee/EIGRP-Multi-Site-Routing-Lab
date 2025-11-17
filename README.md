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
2
<img width="806" height="304" alt="R1 interfaces config 2" src="https://github.com/user-attachments/assets/c16637ba-3979-4d9e-8302-1a54bdc6f36d" />
<img width="514" height="984" alt="R1 interfaces config " src="https://github.com/user-attachments/assets/3425459e-9938-400c-9f22-e2014b7b2221" />
3
<img width="878" height="357" alt="R2 interfaces config 2 " src="https://github.com/user-attachments/assets/c21598e9-7055-4f56-a6dc-a5838eaa98ac" />
<img width="806" height="454" alt="R2 interfaces config 1" src="https://github.com/user-attachments/assets/07e0f93f-b1d8-4143-b8cf-27e86d5943db" />
4
<img width="844" height="613" alt="R3 eigrp configs and test " src="https://github.com/user-attachments/assets/66314958-3686-439b-b025-96577288252b" />
<img width="934" height="630" alt="R2 eigrp configs" src="https://github.com/user-attachments/assets/b2efe043-170d-4b8d-b5b9-4746bf9dcb6f" />
<img width="934" height="623" alt="r1 eigrp config and test " src="https://github.com/user-attachments/assets/b1b50ae8-51d8-4e83-ba18-e3b17f5d695f" />
5
<img width="615" height="123" alt="test connectivity on R3" src="https://github.com/user-attachments/assets/ccd4382e-b081-417a-aa4c-3b4b2e060219" />
<img width="578" height="119" alt="test connectivity on R1" src="https://github.com/user-attachments/assets/496dcfdd-e526-4c4b-a1a0-6d6432ae4ca5" />




