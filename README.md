# Homelab Documentation

Personlig dokumentation til mit homelab. Dette README indeholder nu en samlet oversigt over infrastruktur, netværkstopologi og links til installationsscripts.

## Indhold (TOC)

- Infrastruktur
- Netværkstopologi
- Installationsscripts
- Dokumentation
- TODO

## Infrastruktur

- Proxmox Cluster
- Home Assistant
- Pi-hole

## Netværkstopologi

Dette afsnit beskriver den nuværende netværkstopologi og liste over aktive servere.

### Oversigt

- Netværk: 192.168.1.0/24
- Gateway / Router / Firewall: f.eks. Cloud Gateway Ultra (192.168.1.1)

### Servere

| IP | Hostname | Rolle / noter |
|---|---|---|
| 192.168.1.10 | lv-426.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.11 | lv-223.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.12 | lv-178.nos | Proxmox VE node (Proxmox cluster) |

### Simpel netværkstabel

#### Infrastruktur (fysiske enheder og hovedgateway)

| Device | Rolle | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Internet | Netværk | - | - | - | EWII Bredbånd |
| Cloud Gateway Ultra | Router / Gateway | Internet | 192.168.1.1 | - | Hovedgateway |
| U7 Lite | Access point (AP) | Cloud Gateway Ultra | 192.168.1.187 | - | Trådløst access point |
| USW Flex Mini | Switch | Cloud Gateway Ultra | 192.168.1.168 | - | Edge switch |

#### VLAN 1 (primært klient-netværk)

| Device | Type | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Skynet (SSID) | Wireless network | U7 Lite | - | - | Primært klient-netværk |
| moodeaudio | Raspberry Pi | Cloud Gateway Ultra | 192.168.1.248 | moode.nos | moodeaudio |
| homeassistant | Server | USW Flex Mini | 192.168.1.103 | ha.nos:8123 | Home Assistant server |
| MacBook Air M4 | Client | Skynet | 192.168.1.114 | - | Laptop |
| iPhone | Client | Skynet | 192.168.1.225 | - | Mobiltelefon |
| iPad 10.2 (9th Gen) | Client | Skynet | 192.168.1.177 | - | Tablet |
| Fedora | Client | Skynet | 192.168.1.72 | - | Fedora-baseret workstation |
| lv-178 | Proxmox VE node | USW Flex Mini | 192.168.1.12 | lv-178.nos | Proxmox cluster |
| lv-223 | Proxmox VE node | USW Flex Mini | 192.168.1.11 | lv-223.nos | Proxmox cluster |
| lv-426 | Proxmox VE node | USW Flex Mini | 192.168.1.10 | lv-426.nos | Proxmox cluster |

#### VLAN 10 (isoleret IoT-netværk)

| Device | Type | Parent | IP | Hostname | Notes |
|---|---|---|---|---|---|
| Skynet IoT (SSID) | Wireless network | U7 Lite | - | - | IoT-netværk (isoleret VLAN 10) |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.204 | - | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.104 | - | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.44 | - | Atomi wlan0 |

## Installationsscripts

Foreløbige eksterne scripts (links):

- https://community-scripts.org/scripts/pihole
- https://community-scripts.org/scripts/haos-vm

## Dokumentation

### Proxmox

- Cluster
- Storage
- Backups

### Home Assistant

- Dashboards
- Integrationer
- Automatiseringer

### Netværk

- DNS
- VLANs
- Firewall

## TODO

* [ ] Dokumenter cluster setup
* [ ] Dokumenter DNS setup
* [ ] Dokumenter backup strategi
* [ ] Tilføj installationsvejledning for NixOS og Fedora Workstation (inkl. startskabelon, required packages og konfigurations-eksempler)

## Kontakt og ansvar

- Vedligeholdes af: Mads
- Sidst opdateret: 2026-06-05
