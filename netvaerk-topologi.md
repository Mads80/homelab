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

## Simpelt netværksdiagram (kasse-format)

```
+--------------------+
|      Internet      |
+---------+----------+
          |
+---------------------------+
|  Cloud Gateway Ultra      |
+------+--------+-----------+
       |        |
  +----+----+   +-------------+
  | moode   |   |   U7 Lite   |
  | audio   |   +--+---+------+ 
  +---------+      |   |
                   |   |    +----------------+
                   |   |    |    Skynet      |
                   |   |    +--+---+---+-----+
                   |   |       |   |   |  |
                   |   |       |   |   |  +-- Fedora PC
                   |   |       |   |   +----- iPad
                   |   |       |   +--------- iPhone
                   |   |       +----------- MacBook Air M4
                   |   |
                   |   +----------------+
                   |                    |
                   |                +---+-----------+
                   |                |  Skynet IoT   |
                   |                +----+---+------+ 
                   |                     |   |
                   |                     |   +-- Echo 3
                   |                     +------ Echo 2
                   |                            Echo 1
                   |
                   +----------------------+
                   |    USW Flex Mini     |
                   +----+----+----+-------+
                        |    |    |
                        |    |    +-- lv-426 (Proxmox cluster)
                        |    +------- lv-223 (Proxmox cluster)
                        +------------ lv-178 (Proxmox cluster)
                        +------------ homeassistant
```

## Forslag til næste skridt

- Angiv roller og tjenester for hver server (f.eks. Proxmox-node, Home Assistant, DNS, medie-server).
- Notér VLAN-opdeling og subnet (hvis brugt).
- Tilføj fysisk placering / rack / kabeltræk hvis relevant.
- Opret et diagram i draw.io eller lignende og link her.
- Tilføj DNS-poster og backup-politikker.

## Kontakt og ansvar

- Vedligeholdes af: (indsæt navn)
- Sidst opdateret: 2026-06-05

