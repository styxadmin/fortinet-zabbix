# Zabbix Templates for Fortinet FortiGate devices

## Overview

This template goal is to contain all available SNMP information provided
by a Fortinet FortiGate device.

### Validated Versions
- Zabbix 4.4
- FortiOS 6.2 / 6.4

## Setup
- Download the template
- Import the template and associated them to your devices
- Change the Device Inventory from Disabled (Zabbix default) to Automatic
- There's no need to import the Fortinet MIBs on Zabbix Server, the template is using numeric OIDs

## Zabbix Configuration
You can tune the following macros, which are used by some triggers:
- {$CPU.UTIL.CRIT} = 80
- {$MEMORY.UTIL.MAX} = 80

## Template Links
- Template Module EtherLike-MIB SNMPv2
- Template Module Generic SNMPv2
- Template Module Interfaces SNMPv2

## Discovery Rules
- CPU Cores
- Interfaces

# Items Collected
- CPU
    - CPU usage
    - CPU usage per core (1m and 5s)
    - CPU usage per process type over 1m (System and User)

- Memory
    - Memory usage

- Inventory
    - Serial Number
    - Model Description
    - Operating System
    - Firmware Version

- Session
    - IPv4 Active sessions

- ICMP
    - Loss
    - Response Time

- VPN
    - Active IPsec VPN tunnels
    - Active SSL VPN users
    - SSL VPN state

## Triggers
- CPU
    - High CPU usage

- Memory
    - High memory usage

- ICMP
    - High ICMP ping response time
    - High ICMP ping loss

## Graphs
- CPU
    - CPU usage

- Memory
    - Memory usage

- VPN
    - Active VPN tunnels (IPsec and SSL)

## Host Inventory
This template will automatically populate the following host inventory fields:
- Name
- OS
- OS (Short)
- Serial Number A
- Hardware (Full details)
- Software (Full details)
- Contact
- Location


## Feedback
Please send your comments, requests for additional items and bug reports at the [Issues](https://github.com/barbosm/fortinet-zabbix/issues) session

## Demo
Each items will almost always generate some automatic graphs, here's some samples:

![Active VPN Tunnels][active_vpn_tunnels]

[active_vpn_tunnels]: /static/active_vpn_tunnels.png "Active VPN Tunnels"


## Known Issues
No support for VDOMs at this time

## References
- [Zabbix template guidelines](https://www.zabbix.com/documentation/guidelines/thosts)
- [FortiGate 6.2 SNMP Cookbook](https://docs.fortinet.com/document/fortigate/6.2.0/cookbook/62595/snmp)
