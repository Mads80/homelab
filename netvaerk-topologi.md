# Netværkstopologi

Dette dokument beskriver den nuværende netværkstopologi og liste over aktive servere. Opdater gerne roller, MAC-adresser og tjenester efter behov.

## Oversigt

- Netværk: 192.168.1.0/24
- Gateway / Router / Firewall: f.eks. 192.168.1.1

## Servere

| IP | Hostname | Rolle / noter |
|---|---|---|
| 192.168.1.10 | lv-426.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.11 | lv-223.nos | Proxmox VE node (Proxmox cluster) |
| 192.168.1.12 | lv-178.nos | Proxmox VE node (Proxmox cluster) |

## Simpelt netværksdiagram (tabel)

| Device | Category | Type | Parent | IP / Hostname | VLAN | Notes |
|---|---|---|---|---|---:|---|
| Internet | Infrastructure | Netværk | - | - | - | EWII Bredbånd |
| Cloud Gateway Ultra | Router | Router / Gateway | Internet | - | 1 | Hovedgateway |
| U7 Lite | Access point | Access point | Cloud Gateway Ultra | - | 1 | Trådløst access point |
| USW Flex Mini | Switch | Switch | Cloud Gateway Ultra | - | 1 | Edge switch |
| moodeaudio | Endpoint | Raspberry Pi | Cloud Gateway Ultra | 192.168.1.248 | 1 | moodeaudio |
| Skynet (SSID) | Wireless | Wireless network | U7 Lite | - | 1 | Primært klient-netværk |
| MacBook Air M4 | Client | Laptop | Skynet | 192.168.1.114 | 1 | Laptop |
| iPhone | Client | Mobil | Skynet | 192.168.1.225 | 1 | Mobiltelefon |
| iPad 10.2 (9th Gen) | Client | Tablet | Skynet | 192.168.1.177 | 1 | Tablet |
| Fedora (distro) | Client | Workstation | Skynet | 192.168.1.72 | 1 | Fedora-baseret workstation |
| Skynet IoT (SSID) | Wireless | Wireless network | U7 Lite | - | 10 | IoT-netværk for smarthome-enheder |
| Atomi (wlan0) | IoT device | IoT device | Skynet IoT | 192.168.10.204 | 10 | Atomi wlan0 |
| Atomi (wlan0) | IoT device | IoT device | Skynet IoT | 192.168.10.104 | 10 | Atomi wlan0 |
| Atomi (wlan0) | IoT device | IoT device | Skynet IoT | 192.168.10.44  | 10 | Atomi wlan0 |
| homeassistant | Server | Server | USW Flex Mini | 192.168.1.103 | 1 | Home Assistant server |
| lv-178 | Infrastructure | Proxmox VE node | USW Flex Mini | 192.168.1.12 | 1 | Proxmox cluster |
| lv-223 | Infrastructure | Proxmox VE node | USW Flex Mini | 192.168.1.11 | 1 | Proxmox cluster |
| lv-426 | Infrastructure | Proxmox VE node | USW Flex Mini | 192.168.1.10 | 1 | Proxmox cluster |

## Forslag til næste skridt

- Angiv roller og tjenester for hver server (f.eks. Proxmox-node, Home Assistant, DNS, medie-server).
- Notér VLAN-opdeling og subnet (hvis brugt).
- Tilføj fysisk placering / rack / kabeltræk hvis relevant.
- Opret et diagram i draw.io eller lignende og link her.
- Tilføj DNS-poster og backup-politikker.

## Kontakt og ansvar

- Vedligeholdes af: (indsæt navn)
- Sidst opdateret: 2026-06-05
