---
layout: default
title: MBS Broadcast - RAN Procedures
grand_parent: References and Quick Guides
parent: 5G Multicast Broadcast Services
has_children: false
nav_order: 2
---

# Summary of the RAN procedures to acquire MCCH and MTCH:
  1. Obtain MIB
  2. Obtain SIB1 (points to SIB20)
  3. SIB20 contains configuration of MCCH
  4. Demodulation of MCCH (PDSCH) via PDCCH (with MCCH-RNTI = FFFD)
  5. MCCH contains MBSBroadcastConfiguration
  6. Obtain configuration of MTCH within MBSBroadcastConfiguration and G-RNTIs via mbs-SessionInfoList within MBSBroadcastConfiguration
  7. Demodulation of MTCH (PDSCH) with G-RNTI

# Control Plane
## RRC: MBS Broadcast
### Acquisition of MBS Broadcast information via MCCH
* Procedures in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 5.9**
  * Acquisition of MCCH: via SIB20, included in SIBTypeInfo in SIB1. MCCH transmission indicated via PDCCH (MCCH-RNTI)
  * Configuration information in MCCH via _MBSBroadcastConfiguration_
* _SIB20_ in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 6.2.2**: SIB20 contains the information required to acquire the MCCH/MTCH configuration for MBS broadcast. [**Go to ASN.1**](https://github.com/5G-MAG/Standards/wiki/5G-Multicast-Broadcast-Services-(5MBS):-Relevant-Specifications#sib20).
* _MBSBroadcastConfiguration_ in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 6.2.2**: The MBSBroadcastConfiguration message contains the control information applicable for MBS broadcast services transmitted via broadcast MRB. [**Go to ASN.1**](https://github.com/5G-MAG/Standards/wiki/5G-Multicast-Broadcast-Services-(5MBS):-Relevant-Specifications#MBSBroadcastConfiguration).
 * MBS information elements in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 6.3.6**

### Broadcast MRB configuration
* Procedures in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 5.9.3**
* Broadcast MRB establishment in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 5.9.3.3**
  * Upon a broadcast MRB establishment, the UE shall:
    * establish a PDCP entity and an RLC entity in accordance with MRB-InfoBroadcast for this broadcast MRB included in the MBSBroadcastConfiguration message and the configuration specified in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 9.1.1.7**;
    * configure the MAC layer in accordance with the mtch-SchedulingInfo (if included);
    * configure the physical layer in accordance with the mbs-SessionInfoList, searchSpaceMTCH, and pdsch-ConfigMTCH, applicable for the broadcast MRB;
    * receive DL-SCH on the cell where the MBSBroadcastConfiguration message was received for the established broadcast MRB using g-RNTI and mtch-SchedulingInfo (if included) in this message for this MBS broadcast service;
    * if an SDAP entity with the received mbs-SessionId does not exist:
      * establish an SDAP entity as specified in **[3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) clause 5.1.1**.
      * indicate the establishment of the user plane resources for the mbs-SessionId to upper layers.

* Broadcast MRB release in **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 5.9.3.4**
  * Upon broadcast MRB release for MBS broadcast service, the UE shall:
    * release the PDCP entity, RLC entity as well as the related MAC and physical layer configuration;
    * if the SDAP entity associated with the corresponding mbs-SessionId has no associated MRB:
      * release the SDAP entity, as specified in **[3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) clause 5.1.2**;
      * indicate the release of the user plane resources for the mbs-SessionId to upper layers.

## PDCP: MBS Broadcast
* Procedures in **[3GPP TS 38.323](https://www.3gpp.org/DynaReport/38323.htm) Clause 5**
  * A PDCP entity associated with MRB can be configured by upper layers **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm)** to use header compression. 
  * Protocol data units, formats, and parameters in **[3GPP TS 38.323](https://www.3gpp.org/DynaReport/38323.htm) Clause 6**
  * State variables, constants, and timers in **[3GPP TS 38.323](https://www.3gpp.org/DynaReport/38323.htm) Clause 7**

## RLC: MBS Broadcast
* Procedures in **[3GPP TS 38.322](https://www.3gpp.org/DynaReport/38322.htm)**
  * UM RLC entity in **[3GPP TS 38.322](https://www.3gpp.org/DynaReport/38322.htm) Clause 4.2.1.2**
  * Variables, constants, and timers in **[3GPP TS 38.322](https://www.3gpp.org/DynaReport/38322.htm) Clause 7**

## MAC: MBS Broadcast
* MCCH within DL-SCH in **[3GPP TS 38.321](https://www.3gpp.org/DynaReport/38321.htm) Clause 5.3**
* Value of LCID for MBS broadcast on DL-SCH in **[3GPP TS 38.321](https://www.3gpp.org/DynaReport/38321.htm) Table 6.2.1-1c**
* RNTI values MCCH-RNTI = FFFD in **[3GPP TS 38.321](https://www.3gpp.org/DynaReport/38321.htm) Table 7.1-1**

# User Plane
## SDAP: MBS Broadcast
* SDAP architecture in **[3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) Clause 4.2**
  * The SDAP sublayer is configured for MRBs by RRC. The SDAP sublayer maps MBS QoS flows to MRBs (mapping between an MBS QoS flow and an MRB for DL).
* Data transfer DL in **[3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) Clause 5.2.2**
  * At the reception of an SDAP data PDU from lower layers for a QoS flow, the receiving SDAP entity shall:
    * if this SDAP data PDU is received from an MRB, retrieve the SDAP SDU from the DL SDAP data PDU as specified in **[3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) Clause 6.2.2.1**
* Data PDU without SDAP header in **[3GPP TS 37.324](https://www.3gpp.org/DynaReport/37324.htm) Clause 6.2.2.1**

## PDCP: MBS Broadcast

# Annex: RRC messages ASN.1
For definitions refer to **[3GPP TS 38.331](https://www.3gpp.org/DynaReport/38331.htm) Clause 6.2.2**
## SIB20
```
-- ASN1START
-- TAG-SIB20-START

SIB20-r17 ::=	SEQUENCE {
    mcch-Config-r17                MCCH-Config-r17,
    cfr-ConfigMCCH-MTCH-r17        CFR-ConfigMCCH-MTCH-r17 OPTIONAL,  -- Need S
    lateNonCriticalExtension       OCTET STRING            OPTIONAL,
    ...
}

MCCH-Config-r17 ::= SEQUENCE {
    mcch-RepetitionPeriodAndOffset-r17   MCCH-RepetitionPeriodAndOffset-r17,
    mcch-WindowStartSlot-r17             INTEGER (0..79),
    mcch-WindowDuration-r17              ENUMERATED {sl2, sl4, sl8, sl10, sl20, sl40,sl80, sl160}     OPTIONAL, -- Need S
    mcch-ModificationPeriod-r17          ENUMERATED {rf2, rf4, rf8, rf16, rf32, rf64, rf128, rf256,
                                         rf512, rf1024, r2048, rf4096, rf8192, rf16384, rf32768, rf65536}
}

MCCH-RepetitionPeriodAndOffset-r17 ::= CHOICE {
    rf1-r17                                INTEGER(0),
    rf2-r17                                INTEGER(0..1),
    rf4-r17                                INTEGER(0..3),
    rf8-r17                                INTEGER(0..7),
    rf16-r17                               INTEGER(0..15),
    rf32-r17                               INTEGER(0..31),
    rf64-r17                               INTEGER(0..63),
    rf128-r17                              INTEGER(0..127),
    rf256-r17                              INTEGER(0..255)
}

-- TAG-SIB20-STOP
-- ASN1STOP
```

```
-- ASN1START
-- TAG-CFR-CONFIGMCCH-MTCH-START

CFR-ConfigMCCH-MTCH-r17 ::= SEQUENCE {
    locationAndBandwidthBroadcast-r17          LocationAndBandwidthBroadcast-r17  OPTIONAL,  -- Need S
    pdsch-ConfigMCCH-r17                       PDSCH-ConfigBroadcast-r17          OPTIONAL,  -- Need S
    commonControlResourceSetExt-r17            ControlResourceSet                 OPTIONAL   -- Cond NotSIB1CommonControlResource
}

LocationAndBandwidthBroadcast-r17 ::= CHOICE {
    sameAsSib1ConfiguredLocationAndBW          NULL,
    locationAndBandwidth                       INTEGER (0..37949)
}

-- TAG-CFR-CONFIGMCCH-MTCH-STOP
-- ASN1STOP
```

```
-- ASN1START
-- TAG-PDSCH-CONFIGBROADCAST-START

PDSCH-ConfigBroadcast-r17 ::= SEQUENCE {
    pdschConfigList-r17                    SEQUENCE (SIZE (1..maxNrofPDSCH-ConfigPTM-r17) ) OF PDSCH-ConfigPTM-r17,
    pdsch-TimeDomainAllocationList-r17     PDSCH-TimeDomainResourceAllocationList-r16                          OPTIONAL,   -- Need R
    rateMatchPatternToAddModList-r17       SEQUENCE (SIZE (1..maxNrofRateMatchPatterns)) OF RateMatchPattern   OPTIONAL,   -- Need R
    lte-CRS-ToMatchAround-r17              RateMatchPatternLTE-CRS                                             OPTIONAL,   -- Need R
    mcs-Table-r17                          ENUMERATED {qam256, qam64LowSE}                                     OPTIONAL,   -- Need S
    xOverhead-r17                          ENUMERATED {xOh6, xOh12, xOh18}                                     OPTIONAL    -- Need S
}

PDSCH-ConfigPTM-r17 ::= SEQUENCE {
    dataScramblingIdentityPDSCH-r17        INTEGER (0..1023)         OPTIONAL,   -- Need S
    dmrs-ScramblingID0-r17                 INTEGER (0..65535)        OPTIONAL,   -- Need S
    pdsch-AggregationFactor-r17            ENUMERATED {n2, n4, n8}   OPTIONAL    -- Need S
}

-- TAG-PDSCH-CONFIGBROADCAST-STOP
-- ASN1STOP
```

## MBSBroadcastConfiguration 
```
-- ASN1START
-- TAG-MBSBROADCASTCONFIGURATION-START

MBSBroadcastConfiguration-r17 ::= SEQUENCE {
    criticalExtensions                CHOICE {
        mbsBroadcastConfiguration-r17     MBSBroadcastConfiguration-r17-IEs,
        criticalExtensionsFuture          SEQUENCE {}
    }
}

MBSBroadcastConfiguration-r17-IEs ::= SEQUENCE {
    mbs-SessionInfoList-r17               MBS-SessionInfoList-r17                                              OPTIONAL,   -- Need R
    mbs-NeighbourCellList-r17             MBS-NeighbourCellList-r17                                            OPTIONAL,   -- Need S
    drx-ConfigPTM-List-r17                SEQUENCE (SIZE (1..maxNrofDRX-ConfigPTM-r17)) OF DRX-ConfigPTM-r17   OPTIONAL,   -- Need R
    pdsch-ConfigMTCH-r17                  PDSCH-ConfigBroadcast-r17                                            OPTIONAL,   -- Need S
    mtch-SSB-MappingWindowList-r17        MTCH-SSB-MappingWindowList-r17                                       OPTIONAL,   -- Need R
    lateNonCriticalExtension              OCTET STRING                                                         OPTIONAL,
    nonCriticalExtension                  SEQUENCE {}                                                          OPTIONAL
}

-- TAG-MBSBROADCASTCONFIGURATION-STOP
-- ASN1STOP
```
```
-- ASN1START
-- TAG-MBS-SESSIONINFOLIST-START

MBS-SessionInfoList-r17 ::=      SEQUENCE (SIZE (1..maxNrofMBS-Session-r17)) OF MBS-SessionInfo-r17

MBS-SessionInfo-r17 ::=          SEQUENCE {
    mbs-SessionId-r17                TMGI-r17,
    g-RNTI-r17                       RNTI-Value,
    mrb-ListBroadcast-r17            MRB-ListBroadcast-r17,
    mtch-SchedulingInfo-r17          DRX-ConfigPTM-Index-r17                      OPTIONAL, -- Need S
    mtch-NeighbourCell-r17           BIT STRING (SIZE(maxNeighCellMBS-r17))       OPTIONAL, -- Need S
    pdsch-ConfigIndex-r17            PDSCH-ConfigIndex-r17                        OPTIONAL, -- Need S
    mtch-SSB-MappingWindowIndex-r17  MTCH-SSB-MappingWindowIndex-r17              OPTIONAL  -- Cond MTCH-Mapping
}

DRX-ConfigPTM-Index-r17 ::=          INTEGER (0..maxNrofDRX-ConfigPTM-1-r17)

PDSCH-ConfigIndex-r17  ::=           INTEGER (0..maxNrofPDSCH-ConfigPTM-1-r17)

MTCH-SSB-MappingWindowIndex-r17  ::= INTEGER (0..maxNrofMTCH-SSB-MappingWindow-1-r17)

MRB-ListBroadcast-r17 ::=            SEQUENCE (SIZE (1..maxNrofMRB-Broadcast-r17)) OF MRB-InfoBroadcast-r17

MRB-InfoBroadcast-r17 ::=            SEQUENCE {
    pdcp-Config-r17                      MRB-PDCP-ConfigBroadcast-r17,
    rlc-Config-r17                       MRB-RLC-ConfigBroadcast-r17,
    ...
}

MRB-PDCP-ConfigBroadcast-r17 ::=     SEQUENCE {
    pdcp-SN-SizeDL-r17                   ENUMERATED {len12bits}                   OPTIONAL, -- Need S
    headerCompression-r17                CHOICE {
        notUsed                              NULL,
        rohc                                 SEQUENCE {
            maxCID-r17                           INTEGER (1..16)               DEFAULT 15,
            profiles-r17                         SEQUENCE {
                profile0x0000-r17                    BOOLEAN,
                profile0x0001-r17                    BOOLEAN,
                profile0x0002-r17                    BOOLEAN
           }
        }
    },
    t-Reordering-r17                     ENUMERATED {ms1, ms10, ms40, ms160, ms500, ms1000, ms1250, ms2750}    OPTIONAL -- Need S
}

MRB-RLC-ConfigBroadcast-r17 ::=      SEQUENCE {
    logicalChannelIdentity-r17           LogicalChannelIdentity,
    sn-FieldLength-r17                   ENUMERATED {size6}                       OPTIONAL, -- Need S
    t-Reassembly-r17                     T-Reassembly                             OPTIONAL  -- Need S
}

-- TAG-MBS-SESSIONINFOLIST-STOP
-- ASN1STOP
```
