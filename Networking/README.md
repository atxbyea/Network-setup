## Core switches 

Currently I have 2x HPE 5900AF-4SFP+-2QSFP switches running in my core, these are planned replaced at some point to something smaller, but since I work a lot on Comware their ease of accessibility is quite handy

## Distribution switches

There is currently one HPE 2530G-POE switch used as distribution in the attic, and in my media setup in the main living room there is a TP-Link SG108 plus a TP-Link SG108PoE in my office for testing purposes.

## Wireless

THe primary house WLAN is supplied by a triplet of Linksys Velop access points, these started out 1 wired + 2 wireless mesh, but currently all of them are wired.
No configuration outside of DHCP-address assigned to the uplink port is done, bridged from day one with my primary internal VLAN presented

Additionally I have 3x MSM466 access points that are mostly unused but broadcasting 3 SSIDs on different VLANs as needed (IoT network, wifes malware network and a backup of the primary internal VLAN) these are also used for testing \ config checks of customer issues as needed, on top of this I have 20+ of these in boxes in my garage.
For some odd reason I still have a Cisco Aironet 1200 access point also connected, not used for anything anymore

## DNS

All DHCP clients propegate DNS server automatically in OPNSense, on top of this I create DHCP reservations for all permanently installed hardware, mDNS isn't actively used for anything (afaik the only devices communicating on mDNS in my network is Google Home \ Chromecast devices)

## Wireguard

All my clients (2 laptops, plus one phone) are configued to use Wireguard, they will automatically connect to wireguard upon boot (for laptops) and when connected to !My network on the phone via tasker
