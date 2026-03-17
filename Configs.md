***FARM NETWORK - MAIN CONFIGURATION COMMANDS***



**1.** **OFFICESW**



enable

configure terminal



vlan 10

name OFFICE

exit



vlan 20

name MANAGER

exit



vlan 60

name SERVER\_PRINTER

exit



vlan 70

name CCTV

exit



vlan 80

name STAFF\_WIFI

exit



interface range fa0/1-4

switchport mode access

switchport access vlan 10

exit



interface fa0/5

switchport mode access

switchport access vlan 20

exit



interface range fa0/6-8

switchport mode access

switchport access vlan 60

exit



interface fa0/9

switchport mode access

switchport access vlan 80

exit



interface range fa0/10-11

switchport mode access

switchport access vlan 70

exit



interface fa0/24

switchport mode trunk

exit



end

write memory









**2. SHOPSW**



enable

configure terminal



vlan 30

name SHOP\_POS

exit



vlan 50

name IOT\_MONITORING

exit



vlan 60

name SERVER\_PRINTER

exit



vlan 70

name CCTV

exit



interface range fa0/1-4

switchport mode access

switchport access vlan 30

exit



interface fa0/5

switchport mode access

switchport access vlan 60

exit



interface fa0/6

switchport mode access

switchport access vlan 30

exit



interface range fa0/7-8

switchport mode access

switchport access vlan 50

exit



interface range fa0/9-10

switchport mode access

switchport access vlan 70

exit



interface fa0/24

switchport mode trunk

exit



end

write memory









**3. PYOSW**



enable

configure terminal



vlan 40

name PYO

exit



vlan 60

name SERVER\_PRINTER

exit



vlan 70

name CCTV

exit



vlan 80

name STAFF\_WIFI

exit



interface fa0/1

switchport mode access

switchport access vlan 40

exit



interface fa0/2

switchport mode access

switchport access vlan 60

exit



interface fa0/3

switchport mode access

switchport access vlan 80

exit



interface fa0/4

switchport mode access

switchport access vlan 70

exit



interface fa0/24

switchport mode trunk

exit



end

write memory









**4. GREENHOUSESW**



enable

configure terminal



vlan 50

name IOT\_MONITORING

exit



vlan 70

name CCTV

exit



vlan 80

name STAFF\_WIFI

exit



interface range fa0/1-6

switchport mode access

switchport access vlan 50

exit



interface fa0/7

switchport mode access

switchport access vlan 80

exit



interface range fa0/8-9

switchport mode access

switchport access vlan 70

exit



interface fa0/24

switchport mode trunk

exit



end

write memory









**5. CORESW**



enable

configure terminal



vlan 10

name OFFICE

exit



vlan 20

name MANAGER

exit



vlan 30

name SHOP\_POS

exit



vlan 40

name PYO

exit



vlan 50

name IOT\_MONITORING

exit



vlan 60

name SERVER\_PRINTER

exit



vlan 70

name CCTV

exit



vlan 80

name STAFF\_WIFI

exit



interface fa0/1

switchport mode trunk

exit



interface fa0/2

switchport mode trunk

exit



interface fa0/3

switchport mode trunk

exit



interface fa0/4

switchport mode trunk

exit



interface vlan 10

ip address 192.168.10.1 255.255.255.0

no shutdown

exit



interface vlan 20

ip address 192.168.20.1 255.255.255.0

no shutdown

exit



interface vlan 30

ip address 192.168.30.1 255.255.255.0

no shutdown

exit



interface vlan 40

ip address 192.168.40.1 255.255.255.0

no shutdown

exit



interface vlan 50

ip address 192.168.50.1 255.255.255.0

no shutdown

exit



interface vlan 60

ip address 192.168.60.1 255.255.255.0

no shutdown

exit



interface vlan 70

ip address 192.168.70.1 255.255.255.0

no shutdown

exit



interface vlan 80

ip address 192.168.80.1 255.255.255.0

no shutdown

exit



ip routing



interface gigabitEthernet0/1

no switchport

ip address 192.168.99.2 255.255.255.252

no shutdown

exit



ip route 0.0.0.0 0.0.0.0 192.168.99.1



end

write memory









**6. FARMROUTER**



enable

configure terminal



interface gigabitEthernet0/0

ip address 192.168.99.1 255.255.255.252

no shutdown

exit



ip route 192.168.10.0 255.255.255.0 192.168.99.2

ip route 192.168.20.0 255.255.255.0 192.168.99.2

ip route 192.168.30.0 255.255.255.0 192.168.99.2

ip route 192.168.40.0 255.255.255.0 192.168.99.2

ip route 192.168.50.0 255.255.255.0 192.168.99.2

ip route 192.168.60.0 255.255.255.0 192.168.99.2

ip route 192.168.70.0 255.255.255.0 192.168.99.2

ip route 192.168.80.0 255.255.255.0 192.168.99.2



interface gigabitEthernet0/1

ip address 203.0.113.1 255.255.255.252

no shutdown

exit



end

write memory









**7. WIRELESS SETTINGS**



SSID: FarmStaff

Security: WPA2-PSK

Passphrase: farmwifi123



Note:

The AP model used in Packet Tracer did not expose a simple static management IP workflow in this build, so the main focus remained on SSID/security and successful wireless client connectivity.









**8. STATIC IP SETTINGS**



OfficePC1        192.168.10.11   255.255.255.0   192.168.10.1

OfficePC2        192.168.10.12   255.255.255.0   192.168.10.1

OfficePC3        192.168.10.13   255.255.255.0   192.168.10.1

OfficePC4        192.168.10.14   255.255.255.0   192.168.10.1

ManagerPC        192.168.20.11   255.255.255.0   192.168.20.1



POS1             192.168.30.11   255.255.255.0   192.168.30.1

POS2             192.168.30.12   255.255.255.0   192.168.30.1

POS3             192.168.30.13   255.255.255.0   192.168.30.1

POS4             192.168.30.14   255.255.255.0   192.168.30.1

BarcodeTerminal  192.168.30.21   255.255.255.0   192.168.30.1



PYOTerminal      192.168.40.11   255.255.255.0   192.168.40.1



GHController     192.168.50.11   255.255.255.0   192.168.50.1

HydroController  192.168.50.12   255.255.255.0   192.168.50.1

Zone1Ctrl        192.168.50.13   255.255.255.0   192.168.50.1

Zone2Ctrl        192.168.50.14   255.255.255.0   192.168.50.1

Zone3Ctrl        192.168.50.15   255.255.255.0   192.168.50.1

Zone4Ctrl        192.168.50.16   255.255.255.0   192.168.50.1

FridgeMonitor1   192.168.50.21   255.255.255.0   192.168.50.1

FreezerMonitor1  192.168.50.22   255.255.255.0   192.168.50.1



FarmServer       192.168.60.10   255.255.255.0   192.168.60.1

OfficePrinter    192.168.60.21   255.255.255.0   192.168.60.1

ManagerPrinter   192.168.60.22   255.255.255.0   192.168.60.1

ShopPrinter      192.168.60.23   255.255.255.0   192.168.60.1

PYOPrinter       192.168.60.24   255.255.255.0   192.168.60.1



MainCam1         192.168.70.11   255.255.255.0   192.168.70.1

MainCam2         192.168.70.12   255.255.255.0   192.168.70.1

ShopCam1         192.168.70.21   255.255.255.0   192.168.70.1

ShopCam2         192.168.70.22   255.255.255.0   192.168.70.1

PYOCam1          192.168.70.31   255.255.255.0   192.168.70.1

GHCam1           192.168.70.41   255.255.255.0   192.168.70.1

GHCam2           192.168.70.42   255.255.255.0   192.168.70.1



StaffLaptop1     192.168.80.21   255.255.255.0   192.168.80.1









**9. VERIFICATION COMMANDS**



show vlan brief

show interfaces trunk

show ip interface brief



OfficePC1:

ping 192.168.20.11

ping 192.168.30.11

ping 192.168.60.10



StaffLaptop1:

ping 192.168.80.1

ping 192.168.60.10

ping 192.168.10.11



FarmRouter:

ping 192.168.99.2

ping 192.168.10.1

ping 192.168.60.10

