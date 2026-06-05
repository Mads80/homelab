# Homelab Documentation

Personal documentation for my homelab. This README now contains a consolidated overview of infrastructure, network topology and links to installation scripts.

## Contents (TOC)

- Infrastructure
- Network topology
- Installation scripts
- Documentation
- TODO

## Infrastructure

- Proxmox Cluster
- Home Assistant
- Pi-hole

## Network topology

This section describes the current network topology and active servers.

### Overview

- Network: 192.168.1.0/24
- Gateway / Router / Firewall: e.g. Cloud Gateway Ultra (192.168.1.1)

### Servers

| IP | Hostname | Role / Notes |
|---|---|---|
| 192.168.1.10 | lv-426.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.11 | lv-223.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.12 | lv-178.nos | Proxmox VE node (Proxmox cluster) |

### Simple network tables

#### Infrastructure (physical devices and main gateway)

| Device | Role | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Internet | Network | - | - | - | EWII broadband |
| Cloud Gateway Ultra | Router / Gateway | Internet | 192.168.1.1 | - | Main gateway |
| U7 Lite | Access point (AP) | Cloud Gateway Ultra | 192.168.1.187 | - | Wireless access point |
| USW Flex Mini | Switch | Cloud Gateway Ultra | 192.168.1.168 | - | Edge switch |

#### VLAN 1 (primary client network)

| Device | Type | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Skynet (SSID) | Wireless network | U7 Lite | - | - | Primary client network |
| moodeaudio | Raspberry Pi | Cloud Gateway Ultra | 192.168.1.248 | moode.nos | moodeaudio |
| homeassistant | Server | USW Flex Mini | 192.168.1.103 | ha.nos:8123 | Home Assistant server |
| MacBook Air M4 | Client | Skynet | 192.168.1.114 | - | Laptop |
| iPhone | Client | Skynet | 192.168.1.225 | - | Mobile phone |
| iPad 10.2 (9th Gen) | Client | Skynet | 192.168.1.177 | - | Tablet |
| Fedora | Client | Skynet | 192.168.1.72 | - | Fedora-based workstation |
| lv-178 | Proxmox VE node | USW Flex Mini | 192.168.1.12 | lv-178.nos | Proxmox cluster |
| lv-223 | Proxmox VE node | USW Flex Mini | 192.168.1.11 | lv-223.nos | Proxmox cluster |
| lv-426 | Proxmox VE node | USW Flex Mini | 192.168.1.10 | lv-426.nos | Proxmox cluster |

#### VLAN 10 (isolated IoT network)

| Device | Type | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Skynet IoT (SSID) | Wireless network | U7 Lite | - | - | IoT network (isolated VLAN 10) |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.204 | - | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.104 | - | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.44 | - | Atomi wlan0 |

## Installation scripts

Temporary external script links:

- https://community-scripts.org/scripts/pihole
- https://community-scripts.org/scripts/haos-vm

## Documentation

### Proxmox

- Cluster
- Storage
- Backups

### Home Assistant

- Dashboards
- Integrations
- Automations

### Network

- DNS
- VLANs
- Firewall

## TODO

* [ ] Document cluster setup
* [ ] Document DNS setup
* [ ] Document backup strategy
* [ ] Add installation guide for NixOS and Fedora Workstation (including starter template, required packages and configuration examples)

## Contact & ownership

- Maintained by: Mads
- Last updated: 2026-06-05
