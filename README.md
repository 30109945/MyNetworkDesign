
# ***GREENHOUSE Farm Network Design***



## This repository contains the implementation material for my farm network design assignment.



### Contents

\- `CS3S661\_PCW1\_FarmNetwork\_Final.pkt` - final Cisco Packet Tracer file

\- `configs.txt` - main switch/router configuration commands and test commands

\- `Fig1\_Topology.png` - final topology screenshot

\- `Fig2\_VLAN\_Output.png` - VLAN evidence from an access switch

\- `Fig3\_CoreSW\_Interfaces.png` - CoreSW Layer 3 interface evidence

\- `Fig4\_Wired\_Ping.png` - wired inter-VLAN ping test

\- `Fig5\_Wireless\_Ping.png` - wireless connectivity test

\- `Fig6\_Router\_Ping.png` - router connectivity test



### Network Summary

The farm network includes:

\- main building

\- farm shop

\- PYO kiosk

\- greenhouse area

\- multilayer core switch

\- access switches

\- staff wireless

\- CCTV/monitoring endpoints

\- site router

\- cloud/WAN representation



### VLANs Used

\- VLAN 10 - OFFICE

\- VLAN 20 - MANAGER

\- VLAN 30 - SHOP\_POS

\- VLAN 40 - PYO

\- VLAN 50 - IOT\_MONITORING

\- VLAN 60 - SERVERS\_PRINTERS

\- VLAN 70 - CCTV

\- VLAN 80 - STAFF\_WIFI



##### Notes

Some specialist devices such as CCTV endpoints, greenhouse control nodes, and monitoring terminals were represented using labelled generic Packet Tracer endpoints where exact simulator models were limited or impractical.



Separate Packet Tracer component sensors were considered for greenhouse functions such as temperature, light, humidity, and water monitoring. However, these were not used in the final implementation because they required a lower-level MCU/SBC and component-wiring approach that added complexity without improving the required network design, VLAN structure, addressing, routing, or testing.



### Repository Purpose

This repository is provided as the implementation material for the assignment and contains the Packet Tracer model, evidence screenshots and configuration commands used during the build and testing process.

