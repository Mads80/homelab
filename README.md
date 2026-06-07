# Homelab Documentation

Personal documentation for my homelab. This README now contains a consolidated overview of infrastructure, network topology and links to installation scripts.


## Hardware
- 3× Lenovo ThinkCentre M920q — 16 GB RAM, 256 GB NVMe (boot), 256 GB NVMe (storage)
- Raspberry Pi 2B — Raspberry Pi OS 32bit, running Pi-hole
- Raspberry Pi 3 Model B with HiFiBerry AMP+ HAT
- Cloud Gateway Ultra
- USW Flex Mini
- U7 Lite

## Network topology

This section describes the current network topology and active servers.

### Overview

- Network: 192.168.1.0/24
- Gateway / Router / Firewall: Cloud Gateway Ultra (192.168.1.1)

### Network tables

#### Infrastructure (physical devices and main gateway)

| Device | Role | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Internet | Network | - | - | - | EWII broadband |
| Cloud Gateway Ultra | Router / Gateway | Internet | 192.168.1.1 | - | Main gateway |
| U7 Lite | Access point (AP) | Cloud Gateway Ultra | 192.168.1.187 | - | Wireless access point |
| USW Flex Mini | Switch | Cloud Gateway Ultra | 192.168.1.168 | - | Edge switch |

#### VLAN 1 (primary client network)

| IP | Hostname | Role / Notes |
|---|---|---|
| 192.168.1.10 | lv-426.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.11 | lv-223.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.12 | lv-178.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.127 | pihole.nos | Pi-hole DNS server |
| 192.168.1.130 | pihole2.nos | Raspberry Pi 2B — Raspberry Pi OS |
| 192.168.1.103 | ha.nos:8123 | Home Assistant server |
| 192.168.1.248 | moode.nos | moodeaudio |

| Device | Type | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Skynet (SSID) | Wireless network | U7 Lite | - | - | Primary client network |

#### VLAN 10 (isolated IoT network)

| Device | Type | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Skynet IoT (SSID) | Wireless network | U7 Lite | - | - | IoT network (isolated VLAN 10) |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.204 | - | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.104 | - | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.44 | - | Atomi wlan0 |

## Installation scripts

This section contains an overview of scripts used to install services.

### Pi-hole
Network-wide ad-blocking and DNS server installation:

```bash
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd "Pi-hole/automated install/"
sudo bash basic-install.sh
```

### Links
- https://github.com/pi-hole/pi-hole
- https://community-scripts.org/scripts/pihole
- https://community-scripts.org/scripts/haos-vm 

## Contact & ownership

- Maintained by: Mads
- Last updated: 2026-06-07
