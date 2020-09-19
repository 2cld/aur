[aur.2cld.net](../)

# aur docs
- [aur ops](ops/)
- [aur fix](fix/)

# aur Test Site Reference
- [Blender Shelfs Test](https://www.youtube.com/watch?v=ElGc34VtoA4)
- [FIX: Airflow](fix/airflow.html)
  - Reflective Insulation [Reflectix R-3.7](https://www.menards.com/main/building-materials/insulation/radiant-barrier/reflectix-r-3-7-double-reflective-insulation-with-staple-tab-4-x-100/st48100/p-1444452048523-c-5778.htm) works.
  - [Reference AUR-OPS-AirFlow](https://docs.google.com/spreadsheets/d/1kPnRBxUVTdoFsJWElXbdl48PXVNKeJyo44naDii_eVA)
- [FIX: Sparky](fix/sparky.html) Sparky Issue
  - [Reference AUR-OPS-AvalonPS](https://docs.google.com/spreadsheets/d/1kPnRBxUVTdoFsJWElXbdl48PXVNKeJyo44naDii_eVA)
- [FIX: PDU](fix/pdu.html) PDU Issue

# DNS
- dns issue units were not getting IP
- Check using laptop... no IP but got IP on camper network 192.168.40.x ??
- put in small router on 192.168.40.xx to LAN NAT 192.168.1.1 dhcp with 10 units running fine
- next day they put in more units but only ~ 100 started
- next day on site to look at load issue... 
- I didn't like that all the units were pointed to 8.8.8.8 for dns... that could be a load issue
- began a subnet to handle each hot row rtef1 rtcd1 rtab1
- little router max cpu could only do about 144 dhcp
- portscan off core mikrotik
    - Port 1 - to container poe
    - Port 2 - to container 
    - Port 3 - 192.168.40.0/24 GW: 192.168.40.1 ?? check ??
    - Port 4 - internet main feed to Ubiqity directional
    - Port 5 - none
    - Port 6 - to container
    - Port 7 - 192.168.40.0/24 GW: 192.168.40.1
    - Port 8 - wireless directional pointed north ?? not powered ??
    - Port 9
    - Port 10
    - Port 11
    - Port 12
    - Port 13 - 10.168.247.0/24 GW: 10.168.247.1 ?? check ??
    - Port 14
    - Port 15
    - Port 16
    - Port 17
    - Port 18
    - Port 19
    - Port 20
    - Port 21
    - Port 22
    - Port 23
    - Port 24
- the mikrotik had no issues with the config, so we attempted to put row back into port 13 (which failed)
- did some perf mon on the links, the conclusion was the old link was the best link to use
- we either need to fix the mikrotik OR replace
- suggestion is to verify frequency, load, bandwidth and LAN / WAN routes on all wireless links
- [unifi issue](https://www.reddit.com/r/UNIFI/comments/itml87/beware_unifi_6x_vlan_issues/)
