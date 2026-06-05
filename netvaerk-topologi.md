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

| Device | Type | Parent | IP / Hostname | VLAN | Notes |
|---|---|---|---|---:|---|
| Internet | Netværk | - | - | - | EWII Bredbånd |
| Cloud Gateway Ultra | Router / Gateway | Internet | - | 1 | Hovedgateway |
| moodeaudio | Raspberry Pi | Cloud Gateway Ultra | - | 1 | moodeaudio |
| U7 Lite | Access point | Cloud Gateway Ultra | - | 1 | Trådløst access point |
| Skynet (SSID) | Wireless network | U7 Lite | - | 1 | Primært klient-netværk |
| MacBook Air M4 | Client | Skynet | - | 1 | Laptop |
| iPhone | Client | Skynet | - | 1 | Mobiltelefon |
| iPad 10.2 (9th Gen) | Client | Skynet | - | 1 | Tablet |
| Fedora Workstation | Client | Skynet | - | 1 | Desktop/laptop |
| Skynet IoT (SSID) | Wireless network | U7 Lite | - | 10 | IoT-netværk for smarthome-enheder |
| Echo 1 | IoT device | Skynet IoT | - | 10 | Alexa-enhed |
| Echo 2 | IoT device | Skynet IoT | - | 10 | Alexa-enhed |
| Echo 3 | IoT device | Skynet IoT | - | 10 | Alexa-enhed |
| USW Flex Mini | Switch | Cloud Gateway Ultra | - | 1 | Edge switch |
| homeassistant | Server | USW Flex Mini | - | 1 | Home Assistant server |
| lv-178 | Proxmox VE node | USW Flex Mini | 192.168.1.12 | 1 | Proxmox cluster |
| lv-223 | Proxmox VE node | USW Flex Mini | 192.168.1.11 | 1 | Proxmox cluster |
| lv-426 | Proxmox VE node | USW Flex Mini | 192.168.1.10 | 1 | Proxmox cluster |

## Forslag til næste skridt

- Angiv roller og tjenester for hver server (f.eks. Proxmox-node, Home Assistant, DNS, medie-server).
- Notér VLAN-opdeling og subnet (hvis brugt).
- Tilføj fysisk placering / rack / kabeltræk hvis relevant.
- Opret et diagram i draw.io eller lignende og link her.
- Tilføj DNS-poster og backup-politikker.

## Kontakt og ansvar

- Vedligeholdes af: (indsæt navn)
- Sidst opdateret: 2026-06-05
