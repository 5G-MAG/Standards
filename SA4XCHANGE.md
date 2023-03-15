# 16/03/2023 - SA4 XCHANGE
## Background information
### What we have done:

* Provide insight into specs towards development/implementation (https://www.5g-mag.com/tech-xchanges)
* Foster industry engagement into applications and services (https://www.5g-mag.com/target2023)
* Support development and implementation work (https://developer.5g-mag.com)
* Bring specs to live with demos and trials (https://www.5g-mag.com/tutorials)
* Provide specification feedback to 3GPP (https://www.5g-mag.com/standards - https://github.com/5G-MAG/Standards/projects/2)

### What we have achieved so far:
* The full picture: https://www.5g-mag.com/repositories
* 5G-MAG Reference Tools activity has implemented a Minimum Viable Product for 5G Media Streaming based on downlink Content Hosting and has recently expanded this to include provisioning at reference point M1d and configuration at M3d.
* 5G-MAG now has basic Rel-17 reference implementations the 5GMSd AF and 5GMSd AS that support the key features of Content Hosting for downlink media streaming.
  * Provisioning Sessions, Server Certificates and Content Hosting Configurations can be provisioned in the 5GMSd AF via an implementation of the M1d Provisioning API, complemented by a test client.
  * Server Certificates and Content Hosting Configurations can be configured by the 5GMSd AF in the 5GMSd AS via a simple prototype implementation of an M3d Configuration API, complemented by a test client.
* There are also a basic reference implementation of the Media Player and Media Session Handler for Android.
  * The Media Session Handler, which runs as a shared Android background service, is driven by a basic implementation of the M6 Media Session Handling client API. It can retrieve its configuration for a specific Provisioning Session from the 5GMSd AF using the M5d Service Access Information API.
  * The Media Player is integrated into a simple 5GMSd-Aware Application. Playback is provided by an embedded Exoplayer instance.

### What we intend to do next:
* Continue engaging with standards experts in driving specs beyond the writing work
* Help SA4 spec development based on developers’ feedback. Our GitHub tracker is open to anyone: https://github.com/5G-MAG/Standards/projects/2
  * 5G-MAG and SA4 MBS subworking group have held two joint meetings already (in the run up to SA4#121 Toulouse and SA4#122) and these concentrated on maintenance of TS 26.512 Rel-16 and Rel-17.
  * The changes to that specification agreed recently in Athens are due to go to SA#99 next week for approval and publication, and we have already started to implement them at risk.
  * For the forthcoming meeting cycle, there is a mixture of issues relating to:
    * TS 26.512 (based on the reference implementation experience).
    * TS 26.517 (primarily notifying gaps that have been identified).
  * 5G-MAG is aware that both SA4#123-e and SA4#124 Berlin feed into SA#100 Taipei, so the next opportunity to see agreed changes after Easter will be in late June.

* 5G-MAG intends to participate in the upcoming 3GPP Rel-19 Workshops in our role as Market Representation Partner of 3GPP. We would like to understand the plans for SA4 on such workshops (schedule, thoughts,…)

## Issues to be covered today: https://github.com/5G-MAG/Standards/projects/2
