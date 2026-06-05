# Netværkstopologi

Dette dokument beskriver den nuværende netværkstopologi og liste over aktive servere. Opdater gerne roller, MAC-adresser og tjenester efter behov.

## Oversigt

- Netværk: 192.168.1.0/24
- Gateway / Router / Firewall: f.eks. 192.168.1.1

## Servere

| IP | Hostname | Rolle / noter |
|---|---|---|
| 192.168.1.10 | lv-426.nos | (Udfyld rolle: f.eks. Proxmox / VM-host / tjeneste) |
| 192.168.1.11 | lv-223.nos | (Udfyld rolle) |
| 192.168.1.12 | lv-178.nos | (Udfyld rolle) |

## Simpelt netværksdiagram (ASCII)

Internet
  |
  |  [Router / Firewall]  (192.168.1.1)
  |
  +--[Core Switch]
      |-- lv-426.nos (192.168.1.10)
      |-- lv-223.nos (192.168.1.11)
      |-- lv-178.nos (192.168.1.12)
      |-- (andre enheder: NAS, router admin, access points, osv.)

## Forslag til næste skridt

- Angiv roller og tjenester for hver server (f.eks. Proxmox-node, Home Assistant, DNS, medie-server).
- Notér VLAN-opdeling og subnet (hvis brugt).
- Tilføj fysisk placering / rack / kabeltræk hvis relevant.
- Opret et diagram i draw.io eller lignende og link her.
- Tilføj DNS-poster og backup-politikker.

## Kontakt og ansvar

- Vedligeholdes af: (indsæt navn)
- Sidst opdateret: 2026-06-05

