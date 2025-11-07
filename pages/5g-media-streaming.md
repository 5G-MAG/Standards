---
layout: default
title: 5G Media Streaming
parent: Specifications
has_children: false
nav_order: 0
---

<img src="../assets/images/Banner_5GMS.png" /> 

# 5G Media Streaming Architecture - Relevant Specifications

## Related 3GPP Specifications

The 5G Media Streaming architecture is defined in TS 26.501. Protocols and APIs are specified in TS 26.512, with reference to the generalized Media Session Handling to TS 26.510. Profiles, codecs and formats are provided in TS 26.511.

* **[3GPP TS 26.501](https://www.3gpp.org/dynareport/26501.htm) - 5G Media Streaming (5GMS); General description and architecture**
* **[3GPP TS 26.512](https://www.3gpp.org/dynareport/26512.htm) - 5G Media Streaming (5GMS); Protocols**
* **[3GPP TS 26.510](https://www.3gpp.org/dynareport/26510.htm) - Media delivery; interactions and APIs for provisioning and media session handling**
* **[3GPP TS 26.511](https://www.3gpp.org/dynareport/26511.htm) - 5G Media Streaming (5GMS); Profiles, codecs and formats**

### Features: Content Hosting (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M1 | 5.2.2 | Provisioning Sessions API | 8.2
M1 | 5.2.3 | Content protocols discovery API | 8.3
M1 | 5.2.4 | Server Certificates provisioning API | 8.4
M1 | 5.2.5 | Content Preparation Templates provisioning API | 8.5
M1 | 5.2.6 | Edge Resources provisioning API | 8.6
M1 | 5.2.7 | Policy Templates provisioning API | 8.7
M1 | 5.2.8 | Content Hosting provisioning API | 8.8
M5 | 5.3.2 | Service Access Information API | 9.2

### Features: Content Publishing (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M1 | 5.2.2 | Provisioning Sessions API | 8.2
M1 | 5.2.3 | Content protocols discovery API | 8.3
M1 | 5.2.4 | Server Certificates provisioning API | 8.4
M1 | 5.2.5 | Content Preparation Templates provisioning API | 8.5
M1 | 5.2.6 | Edge Resources provisioning API | 8.6
M1 | 5.2.7 | Policy Templates provisioning API | 8.7
M1 | 5.2.9 | Content Publishing provisioning API | 8.9
M5 | 5.3.2 | Service Access Information API | 9.2

### Features: Dynamic Policy instantiation (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M1 | 5.2.2 | Provisioning Sessions API | 8.3
M1 | 5.2.7 | Policy Templates provisioning API | 8.7
M5 | 5.3.2 | Service Access Information API | 9.2
M5 | 5.3.3 | Dynamic Policies API | 9.3

### Features: Network Assistance (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M5 | 5.3.2 | Service Access Information API | 9.2
M5 | 5.3.4 | Network Assistance API | 9.4

### Features: QoE Metrics reporting (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M1 | 5.2.2 | Provisioning Sessions API | 8.3
M1 | 5.2.11 | Metrics Reporting provisioning API | 8.10
M5 | 5.3.2 | Service Access Information API | 9.2
M5 | 5.3.5 | Metrics Reporting API | 9.5

### Features: Consumption reporting (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M1 | 5.2.2 | Provisioning Sessions API | 8.3
M1 | 5.2.12 | Consumption Reporting provisioning API | 8.12
M5 | 5.3.2 | Service Access Information API | 9.2
M5 | 5.3.6| Consumption Reporting API | 9.6

### Features: UE data collection, reporting and exposure (TS 26.510)

Reference Point | Interactions | API Name | API
--- | --- | --- | ---
M1 | 5.2.13 | Event Data Processing provisioning API | 8.13
M5 | 5.3.5 | Metrics Reporting API | 9.5
M5 | 5.3.6 | Consumption Reporting API | 9.6

## Release-19 Advanced Media Delivery

Technical Reports: 
* **[3GPP TR 26.804](https://www.3gpp.org/dynareport/26804.htm) - Study on 5G media streaming extensions**
* **[3GPP TR 26.802](https://www.3gpp.org/dynareport/26802.htm) - Multicast Architecture Enhancement for 5G Media Streaming**

### Common Media Client Data (CMCD)

* **Specification: [CTA-5004](https://cdn.cta.tech/cta/media/media/resources/standards/pdfs/cta-5004-final.pdf) - Web Application Video Ecosystem - Common Media Client Data**
  * Complementary information: [https://dashif.org/events/special-sessions/#special-sessions-2022](https://dashif.org/events/special-sessions/#special-sessions-2022)
* Stage 3 support summarized in the following CRs: [S4-251463](https://www.3gpp.org/ftp/tsg_sa/WG4_CODEC/TSGS4_133-e/Docs/S4-251463.zip) (26.510) and [S4aI250146](https://www.3gpp.org/ftp/TSG_SA/WG4_CODEC/3GPP_SA4_AHOC_MTGs/SA4_MBS/Docs/S4aI250146.zip) (26.512)

* Metrics Reporting Provisining API via M1 defined in TS 26.510, 8.11, with `scheme` property defined in TS 26.512, 7.8. Service Access Information provided to Media Session Handler via M5.
* In-band client reporting on M4 (Media Stream Handler - Application Server) defined in TS 26.512, 10.5
* Client data reporting on M3 (Application Server - Application Function) defined in TS 26.512, 11.4.3
* Inband client reporting in DASH, defined in TS 26.512, Annex G.5

#### Alternatives
* Configuration of Reporting via Service URL defined in TS 26.512, 12.4
* Configurations and settings API for Media Player via M7d (5GMSd-Aware Application) and M11d (Media Session Handler) defined in clause 13.2.4 of TS 26.512

#### Event exposure to NWDAF or Event Consumer AF
* Event exposure on R5/R6 defined in clause 18.3.3 of TS 26.512

### Coded Multisource Media Format (CMMF)

* **Specification: [ETSI TS 103 973](https://www.etsi.org/deliver/etsi_ts/103900_103999/103973/01.01.01_60/ts_103973v010101p.pdf) - Coded Multisource Media Format (CMMF) for Content Distribution and Delivery**
