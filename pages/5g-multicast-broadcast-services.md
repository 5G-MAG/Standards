---
layout: default
title: 5G Multicast Broadcast Services
parent: References and Quick Guides
has_children: true
nav_order: 6
---

# 5G Multicast Broadcast Services (MBS)

## Related 3GPP Specifications

This is a list of specifications in the scope of 5G Multicast Broadcast Services.

### MBS User Services
* [3GPP TS 26.502](https://www.3gpp.org/DynaReport/26502.htm) - 5G Multicast-Broadcast Services; User service architecture
* [3GPP TS 26.517](https://www.3gpp.org/DynaReport/26517.htm) - 5G Multicast-Broadcast User Services; Protocols and Formats
* [3GPP TS 29.580](https://www.3gpp.org/DynaReport/29580.htm) - 5G System; Multicast/Broadcast Service Function services; Stage 3
* [3GPP TS 29.581](https://www.3gpp.org/DynaReport/29581.htm) - 5G System; Multicast/Broadcast Service Transport Services; Stage 3

### 5G Core Network specifications

#### MBS architecture
* [3GPP TS 23.247](https://www.3gpp.org/DynaReport/23247.htm) - Architectural enhancements for 5G multicast-broadcast services

#### Network Function services
* [3GPP TS 29.532](https://www.3gpp.org/DynaReport/29532.htm) - 5G System; 5G Multicast-Broadcast Session Management Services; Stage 3
* [3GPP TS 29.537](https://www.3gpp.org/DynaReport/29537.htm) - 5G System; Multicast/Broadcast Policy Control services; Stage 3
#### Protocols
* [3GPP TS 29.244](https://www.3gpp.org/DynaReport/29244.htm) - Interface between the Control Plane and the User Plane nodes
* [3GPP TS 38.413](https://www.3gpp.org/DynaReport/38413.htm) - NG-RAN; NG Application Protocol (NGAP)
* [3GPP TS 24.501](https://www.3gpp.org/DynaReport/24501.htm) - Non-Access-Stratum (NAS) protocol for 5G System (5GS); Stage 3
* [3GPP TS 29.281](https://www.3gpp.org/DynaReport/29281.htm) - General Packet Radio System (GPRS) Tunnelling Protocol User Plane (GTPv1-U)

##### Control plane
* PFCP (29.244)
* NGAP (38.413)
* NAS (24.501)

##### User plane
* GTPU (29.281)

### NR and NG-RAN specifications
* [3GPP TS 38.300](https://www.3gpp.org/DynaReport/38300.htm) - NR; NR and NG-RAN Overall Description
* [3GPP TS 38.401](https://www.3gpp.org/DynaReport/38401.htm) - NG-RAN; Architecture description

#### NR
* [3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) - NR; Radio Resource Control (RRC) Protocol Specification
* [3GPP TS 38.321](https://www.3gpp.org/DynaReport/38321.htm) - NR; Medium Access Control (MAC) Protocol Specification
* [3GPP TS 38.322](https://www.3gpp.org/DynaReport/38322.htm) - NR; Radio Link Control (RLC) Protocol Specification
* [3GPP TS 38.323](https://www.3gpp.org/DynaReport/38323.htm) - NR; Packed Data Convergence Protocol (PDCP) Specification
* [3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) - E-UTRA and NR; Service Data Adaptation Protocol (SDAP) Specification
* [3GPP TS 38.211](https://www.3gpp.org/DynaReport/38211.htm) - NR; Physical channels and modulation
* [3GPP TS 38.212](https://www.3gpp.org/DynaReport/38212.htm) - NR; Multiplexing and channel coding
* [3GPP TS 38.213](https://www.3gpp.org/DynaReport/38213.htm) - NR; Physical layer procedures for control
* [3GPP TS 38.214](https://www.3gpp.org/DynaReport/38214.htm) - NR; Physical layer procedures for data

##### Control plane (PSS/SSS/PBCH(MIB), PDCCH, PDSCH(SIB20/SIB21/MCCH)):
* RRC (38.331)
* PDCP (38.323)
* RLC (38.322)
* MAC (38.321)
* PHY (38.211, 38.212, 38.213, 38.214)

##### User plane (PDSCH (MTCH)):
* SDAP (37.324)
* PDCP (38.323)
* RLC (38.322)
* MAC (38.321)
* PHY (38.211, 38.212, 38.213, 38.214)

#### NG-RAN
* [3GPP TS 38.420](https://www.3gpp.org/DynaReport/38420.htm) - NG-RAN; Xn general aspects and principles
* [3GPP TS 38.423](https://www.3gpp.org/DynaReport/38423.htm) - NG-RAN; Xn Application Protocol (XnAP)
* [3GPP TS 38.410](https://www.3gpp.org/DynaReport/38410.htm) - NG-RAN; NG general aspects and principles
* [3GPP TS 38.413](https://www.3gpp.org/DynaReport/38413.htm) - NG-RAN; NG Application Protocol (NGAP)
* [3GPP TS 38.470](https://www.3gpp.org/DynaReport/38470.htm) - NG-RAN; F1 general aspects and principles
* [3GPP TS 38.473](https://www.3gpp.org/DynaReport/38473.htm) - NG-RAN; F1 application protocol (F1AP)
* [3GPP TS 38.460](https://www.3gpp.org/DynaReport/38460.htm) - NG-RAN; E1 general aspects and principles
* [3GPP TS 38.463](https://www.3gpp.org/DynaReport/38463.htm) - NG-RAN; E1 application protocol (E1AP)
* [3GPP TS 38.415](https://www.3gpp.org/DynaReport/38415.htm) - NG-RAN; PDU Session User Plane Protocol
* [3GPP TS 38.425](https://www.3gpp.org/DynaReport/38425.htm) - NG-RAN; NR user plane protocol

##### Interfaces
* Xn (38.420,38.423): Connect two gNBs
* NG (38.410,38.413): NG-c = N2 (AMF); NG-u = N3 (UPF)
* F1 (38.470,38.473): F1-c (PDCP-c to RLC); F1-u (PDCP-u to RLC)
* E1 (38.460,38.463): CU-CP (RRC + PDCP-c) to CU-UP (SDAP + PDCP-u)


