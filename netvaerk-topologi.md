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
| <mark>Cloud Gateway Ultra</mark> | <mark>Router / Gateway</mark> | <mark>Internet</mark> | <mark>-</mark> | <mark>1</mark> | <mark>Hovedgateway</mark> |
| moodeaudio | Raspberry Pi | Cloud Gateway Ultra | 192.168.1.248 | 1 | moodeaudio |
| <mark>U7 Lite</mark> | <mark>Access point</mark> | <mark>Cloud Gateway Ultra</mark> | <mark>-</mark> | <mark>1</mark> | <mark>Trådløst access point (AP)</mark> |
| Skynet (SSID) | Wireless network | U7 Lite | - | 1 | Primært klient-netværk |
| MacBook Air M4 | Client | Skynet | 192.168.1.114 | 1 | Laptop |
| iPhone | Client | Skynet | 192.168.1.225 | 1 | Mobiltelefon |
| iPad 10.2 (9th Gen) | Client | Skynet | 192.168.1.177 | 1 | Tablet |
| Fedora (distro) | Client | Skynet | 192.168.1.72 | 1 | Fedora-baseret workstation |
| Skynet IoT (SSID) | Wireless network | U7 Lite | - | 10 | IoT-netværk (isoleret VLAN 10) |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.204 | 10 | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.104 | 10 | Atomi wlan0 |
| Atomi (wlan0) | IoT device | Skynet IoT | 192.168.10.44  | 10 | Atomi wlan0 |
| <mark>USW Flex Mini</mark> | <mark>Switch</mark> | <mark>Cloud Gateway Ultra</mark> | <mark>-</mark> | <mark>1</mark> | <mark>Edge switch</mark> |
| homeassistant | Server | USW Flex Mini | 192.168.1.103 | 1 | Home Assistant server |
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
