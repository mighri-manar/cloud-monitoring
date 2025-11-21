# Network Security & Monitoring Infrastructure

![Project Status](https://img.shields.io/badge/Status-Active%20Development-green)
![Phase](https://img.shields.io/badge/Phase-3%20Complete-blue)
![Network](https://img.shields.io/badge/Routers-10%20Cisco-blue)
![MPLS](https://img.shields.io/badge/MPLS-LDP%20Enabled-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)
![GNS3](https://img.shields.io/badge/GNS3-Network%20Simulation-red)
![Security](https://img.shields.io/badge/Security-HIDS%2FNIDS-critical)

## 🎯 Project Overview

This project implements a comprehensive network security and monitoring solution using HIDS/NIDS technologies. The infrastructure combines MPLS networking, virtualization, security appliances, and advanced monitoring tools to create a production-grade network security architecture.

### Project Theme
**HIDS/NIDS Solutions** - Host and Network Intrusion Detection Systems with integrated monitoring and analysis capabilities.


## 🌐 Live Documentation

**GitHub Pages Site**: [https://mighri-manar.github.io/cloud-monitoring/](https://mighri-manar.github.io/cloud-monitoring/)

- **Homepage**: [https://mighri-manar.github.io/cloud-monitoring/](https://mighri-manar.github.io/cloud-monitoring/)
- **Network Topology**: [https://mighri-manar.github.io/cloud-monitoring/network-topology-summary.html](https://mighri-manar.github.io/cloud-monitoring/network-topology-summary.html)

View the complete network topology documentation online without cloning the repository!


## 🏗️ Architecture

### Network Topology
- **Core Layer**: MPLS-enabled provider network (R1, R2)
- **Provider Edge**: Customer-facing routers with MPLS (R3, R4)
- **Distribution Layer**: Redundant connections (R5)
- **Edge Services**: Internet gateway with NAT (R6)
- **Service Layer**: DMZ and monitoring networks (R7, R8)
- **Customer Edge**: Isolated client networks (C1, C2)

### Technology Stack

#### Virtualization Platform
- **GNS3 VM** (192.168.182.128) - Network simulation environment
- **VMware Workstation 15 Pro** - Virtual machine management
- Cisco IOS C3700 router images / IOSv

#### Virtual Machines
| VM | IP Address | Purpose | Status |
|---|---|---|---|
| Asterisk VM | 192.168.70.10 | Service testing (FTP, etc.) | ✅ Configured |
| RADIUS VM | 192.168.71.2 | Authentication server | ✅ Configured |
| Client1-1 | 192.168.9.10 | Test workstation | ✅ Configured |
| Nagios XI | TBD | Network monitoring | ⏳ Planned |
| ELK Stack | TBD | Log analysis & SIEM | ⏳ Planned |
| Wazuh | TBD | Security monitoring | ⏳ Planned |

---

## 📊 Current Implementation Status

### ✅ Phase 1: Core Network Infrastructure (COMPLETED)

#### MPLS Provider Network
- **10 Cisco Routers** configured with IOS 12.4
- **MPLS LDP** enabled on core routers (R1-R6)
- **OSPF Area 0** for dynamic routing
- **Redundant paths** for high availability

#### Network Features
- ✅ 24 subnets (18 P2P + 6 service networks)
- ✅ Loopback interfaces for router IDs
- ✅ Multiple redundant links between core routers
- ✅ Point-to-point /30 subnets for efficient addressing

#### Routing Configuration
- ✅ OSPF dynamic routing across all routers
- ✅ Default route injection from R6
- ✅ Static routes for service network access
- ✅ Route redistribution between MPLS and customer networks

### ✅ Phase 2: Internet & Edge Services (COMPLETED)

#### Internet Gateway (R6)
- ✅ NAT Overload (PAT) configuration
- ✅ Default route to internet (192.168.182.2)
- ✅ DNS servers configured (8.8.8.8, 8.8.4.4)
- ✅ ACL 1 for NAT traffic filtering

#### DMZ Services (R7)
- ✅ Asterisk VM integration (service testing environment)
- ✅ RADIUS authentication server integration
- ✅ AAA configuration with RADIUS
- ✅ VTY line authentication via RADIUS
- ✅ ACL 101 inbound filtering

#### Service Testing
- ✅ FTP server tested on Asterisk VM
- ✅ RADIUS authentication tested with R7 as client
- ✅ Client-to-service connectivity verified

### ✅ Phase 3: Security Baseline (COMPLETED)

#### Authentication & Authorization
- ✅ RADIUS server (192.168.71.2) with testing123 key
- ✅ AAA new-model enabled on R7
- ✅ RADIUS authentication for VTY access
- ✅ Local fallback authentication

#### Network Segmentation
- ✅ DMZ network isolation (192.168.7.0/24)
- ✅ Monitoring network separation (192.168.8.0/24)
- ✅ Customer edge segregation (C1, C2)
- ✅ Service network VLANs

---

## 🚀 Implementation Roadmap

### ⏳ Phase 4: Advanced Security (IN PROGRESS)

#### Access Control Lists (ACLs)
- [ ] Extended ACLs for traffic filtering
- [ ] Interface-level security policies
- [ ] Anti-spoofing rules
- [ ] Rate limiting configurations

#### Fortigate Integration
- [ ] Fortigate VM deployment
- [ ] Next-generation firewall rules
- [ ] IPS/IDS signature configuration
- [ ] Application control policies
- [ ] Web filtering and SSL inspection

#### Enhanced Filtering
- [ ] PfSense firewall deployment
- [ ] IPsec VPN tunnels
- [ ] Site-to-site VPN between customer sites
- [ ] Remote access VPN configuration

### ⏳ Phase 5: Monitoring & Observability (PLANNED)

#### Nagios XI Deployment
- [ ] CentOS 7 / Ubuntu Server installation
- [ ] Network device monitoring configuration
- [ ] SNMP v2 manager + agents setup
- [ ] Service checks (ICMP, SSH, HTTP, etc.)
- [ ] Alert notifications
- [ ] Performance graphing with Cacti integration
- [ ] KPI dashboard creation

#### Network Analysis Tools
- [ ] Wireshark packet capture setup
- [ ] Traffic analysis and baselining
- [ ] Ostinato traffic generator configuration
- [ ] Network stress testing
- [ ] QoS simulation and testing
- [ ] Convergence time measurements

### ⏳ Phase 6: SIEM & Log Management (PLANNED)

#### ELK Stack Deployment
- [ ] Elasticsearch cluster setup
- [ ] Logstash configuration for log parsing
- [ ] Kibana dashboard creation
- [ ] Filebeat agents on network devices
- [ ] TShark API integration for packet analysis
- [ ] JSON log transformation pipeline
- [ ] Custom KPI visualizations
- [ ] Security event correlation

#### Alternative SIEM Options
- [ ] Graylog evaluation
- [ ] Prometheus + Grafana integration
- [ ] Amazon CloudWatch integration (if cloud migration)

### ⏳ Phase 7: Security Monitoring (PLANNED)

#### Wazuh HIDS/NIDS
- [ ] Wazuh manager installation
- [ ] Agent deployment on VMs and routers
- [ ] File integrity monitoring
- [ ] Vulnerability detection
- [ ] Security compliance monitoring (PCI-DSS, GDPR)
- [ ] Active response configuration
- [ ] Integration with ELK stack
- [ ] Custom security rules and alerts

### ⏳ Phase 8: Containerization & Cloud (FUTURE)

#### Container Platform
- [ ] Docker (libcontainer) deployment
- [ ] RKT (Rocket) evaluation
- [ ] Microservices architecture for monitoring tools
- [ ] Container orchestration

#### Cloud Migration
- [ ] Elastic Cloud dashboard deployment
- [ ] Hybrid cloud monitoring
- [ ] Cloud-native security tools

---

## 📁 Repository Structure

```
├── configs/
│   ├── routers/           # Router running-configs (R1-R8, C1, C2)
│   ├── vms/               # VM configurations
│   └── services/          # Service configs (RADIUS, FTP, etc.)
├── docs/
│   ├── GNS3-Network-Topology-Summary.pdf  # Complete network documentation
│   ├── topology/          # Network diagrams and GNS3 project files
│   ├── ip-addressing.md   # IP addressing scheme
│   └── setup-guides/      # Step-by-step configuration guides
├── monitoring/
│   ├── nagios/           # Nagios configurations (planned)
│   ├── elk/              # ELK stack configs (planned)
│   └── wazuh/            # Wazuh HIDS configs (planned)
├── security/
│   ├── acls/             # Access control lists
│   ├── firewall/         # Fortigate/PfSense configs (planned)
│   └── vpn/              # IPsec VPN configurations (planned)
├── scripts/
│   ├── automation/       # Network automation scripts
│   └── testing/          # Testing and validation scripts
└── README.md
```

---

## 🔧 Technologies & Tools

### Networking
- **Routing Protocol**: OSPF (Open Shortest Path First)
- **Label Switching**: MPLS with LDP
- **NAT**: PAT/Overload on R6
- **Services**: DHCP, FTP/TFTP, SNMP v2

### Security
- **Authentication**: RADIUS (FreeRADIUS)
- **Firewall**: Fortigate / PfSense (planned)
- **VPN**: IPsec (planned)
- **ACLs**: Cisco extended ACLs (in progress)

### Monitoring & Analysis
- **Network Monitoring**: Nagios XI (planned)
- **Metrics**: Cacti / Zabbix (planned)
- **SIEM**: ELK Stack (planned)
- **HIDS/NIDS**: Wazuh (planned)
- **Traffic Analysis**: Wireshark, TShark
- **Traffic Generation**: Ostinato

### Visualization
- **Dashboards**: Kibana, Grafana (planned)
- **Graphing**: Plotly libraries (planned)
- **KPIs**: Custom dashboards (planned)

---

## 🌐 Network Details

### IP Addressing Scheme

#### Core Networks (MPLS)
- **Loopback IDs**: 1.1.1.1 - 6.6.6.6 (/32)
- **P2P Links**: 10.0.1.0/30 - 10.0.23.0/30

#### Service Networks
- **DMZ Services**: 192.168.7.0/24 (R7 Loopback0)
- **Monitoring**: 192.168.8.0/24 (R8 Loopback0)
- **Client 1**: 192.168.9.0/24 (C1 network)
- **Client 2**: 192.168.10.0/24 (C2 network)
- **Asterisk/Test**: 192.168.70.0/24 (Service testing)
- **RADIUS Auth**: 192.168.71.0/24 (Authentication)
- **Internet/WAN**: 192.168.182.0/24 (R6 external)

### Router Management
| Router | Telnet Port | Management IP | Auth Method |
|--------|-------------|---------------|-------------|
| R1 | localhost:5000 | 1.1.1.1 | Login |
| R2 | localhost:5001 | 2.2.2.2 | Login |
| R3 | localhost:5002 | 3.3.3.3 | Login |
| R4 | localhost:5003 | 4.4.4.4 | Login |
| R5 | localhost:5004 | 5.5.5.5 | Login |
| R6 | localhost:5005 | 6.6.6.6 | Login |
| R7 | localhost:5006 | 192.168.7.1 | RADIUS |
| R8 | localhost:5007 | 192.168.8.1 | Login |
| C1 | localhost:5008 | 192.168.9.1 | Login |
| C2 | localhost:5009 | 192.168.10.1 | Login |

---

## 🚦 Getting Started

### Prerequisites
- GNS3 (latest version)
- VMware Workstation 15 Pro
- Cisco IOS images (C3700 or IOSv)
- Linux VMs (CentOS 7 / Ubuntu 18.04)
- Windows 10 VM (optional)
- Minimum 16GB RAM recommended
- 100GB free disk space

### Quick Start

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/network-security-monitoring.git
cd network-security-monitoring
```

2. **Review network documentation**
   - Check out `docs/GNS3-Network-Topology-Summary.pdf` for complete network details
   - Review IP addressing scheme and router configurations

3. **Import GNS3 topology**
   - Open GNS3
   - Import the topology file from `docs/topology/`
   - Configure VM connections

3. **Load router configurations**
```bash
# Copy configs from configs/routers/ to each router
# Or use the provided automation script
./scripts/load-configs.sh
```

4. **Deploy VMs**
   - Import VM templates from `configs/vms/`
   - Configure network adapters according to topology
   - Start VMs and verify connectivity

5. **Verify connectivity**
```bash
# Test OSPF neighbors
show ip ospf neighbor

# Test MPLS LDP
show mpls ldp neighbor

# Test routing
show ip route
```

---

## 📝 Configuration Examples

### MPLS LDP Configuration
```cisco
mpls label protocol ldp
mpls ldp router-id Loopback0 force

interface FastEthernet0/0
 mpls ip
```

### OSPF Configuration
```cisco
router ospf 1
 log-adjacency-changes
 network 10.0.0.0 0.255.255.255 area 0
```

### RADIUS AAA Configuration
```cisco
aaa new-model
aaa authentication login default group radius local
aaa authentication login RAD_AUTH group radius local

radius-server host 192.168.71.2 auth-port 1812 acct-port 1813 key testing123

line vty 0 4
 login authentication RAD_AUTH
```

### NAT Overload Configuration
```cisco
interface GigabitEthernet6/0
 ip nat outside

interface FastEthernet0/0
 ip nat inside

ip nat inside source list 1 interface GigabitEthernet6/0 overload
access-list 1 permit 10.0.0.0 0.255.255.255
```

---

## 🧪 Testing Procedures

### Network Connectivity Tests
```bash
# Ping test from client to internet
ping 8.8.8.8

# Traceroute to verify MPLS path
traceroute 192.168.70.10

# OSPF verification
show ip ospf database
show ip ospf interface brief
```

### RADIUS Authentication Test
```bash
# Test RADIUS from R7
test aaa group radius server 192.168.71.2 username testuser password testpass

# Verify authentication logs on RADIUS server
tail -f /var/log/radius/radius.log
```

### Service Testing
```bash
# FTP connectivity test
ftp 192.168.70.10

# SNMP walk (when implemented)
snmpwalk -v2c -c public 10.0.1.1
```

---

## 📈 Monitoring & KPIs (Planned)

### Key Performance Indicators
- Network uptime and availability
- Link utilization percentages
- OSPF convergence time
- Packet loss and latency metrics
- Security events per hour
- Failed authentication attempts
- Intrusion detection alerts

### Dashboards
- Real-time network topology
- Traffic flow visualization
- Security event timeline
- Device health status
- Bandwidth utilization graphs

---

## 🔐 Security Considerations

### Current Security Measures
- ✅ Network segmentation (DMZ, monitoring, client networks)
- ✅ RADIUS centralized authentication
- ✅ NAT for internal IP hiding
- ✅ Basic ACL filtering

### Planned Security Enhancements
- Extended ACLs for granular traffic control
- Fortigate next-gen firewall with IPS/IDS
- IPsec VPN for secure site-to-site connectivity
- Wazuh HIDS for intrusion detection
- ELK SIEM for security event correlation
- Automated threat response

---

## 🤝 Contributing

This is an academic project for network security and monitoring implementation. Contributions, suggestions, and improvements are welcome!

### Contribution Guidelines
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/ACL-implementation`)
3. Commit your changes (`git commit -m 'Add extended ACLs for R3'`)
4. Push to the branch (`git push origin feature/ACL-implementation`)
5. Open a Pull Request

---

## 📚 References & Resources

### Documentation
- [Cisco MPLS Configuration Guide](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/mp_ldp/configuration/xe-16/mp-ldp-xe-16-book.html)
- [OSPF Design Guide](https://www.cisco.com/c/en/us/support/docs/ip/open-shortest-path-first-ospf/7039-1.html)
- [Nagios XI Documentation](https://assets.nagios.com/downloads/nagiosxi/docs/Nagios-XI-Documentation.pdf)
- [ELK Stack Guide](https://www.elastic.co/guide/index.html)
- [Wazuh Documentation](https://documentation.wazuh.com/)
- [Fortigate Administration Guide](https://docs.fortinet.com/)

### Learning Resources
- GNS3 Network Simulation
- Cisco CCNP Enterprise
- Network Security Best Practices
- SIEM Implementation Guides

---

## 📧 Contact

**Project Author**: [Manar Mighri]  
**Email**: [mighrimanar11@gmail.com]  
**GitHub**: [@mighri-manar](https://github.com/mighri-manar)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.



---

**Project Status**: 🟢 Active Development  
**Last Updated**: November 21st 2025  
**Current Phase**: Phase 3 Complete - Moving to Phase 4 (Advanced Security)

---

## ⭐ Project Highlights

- ✨ 10-router MPLS network with full redundancy
- ✨ Production-grade network design with segmentation
- ✨ Integration of multiple security and monitoring technologies
- ✨ Hands-on implementation of industry-standard tools
- ✨ Complete SIEM and HIDS/NIDS solution (upon completion)

---

*This project demonstrates practical implementation of enterprise network security architecture, combining traditional networking with modern security and monitoring practices.*
