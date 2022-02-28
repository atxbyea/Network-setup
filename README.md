# Network-setup

General documentation of my home network setup, including but not limited to 

*Services
*Routing \ Firewalls \ Networking
*Hardening
*Logging
*Backup


## Services

### Docker

* Docker-CE engine currently running on two hosts - Mirai and Kakuzu
* Docker-compose used to simplify deployment and updates

### KVM

* KVM used to host always running services on my always on powerhouse - Mirai

### VMware vSphere portfolio

* Running a full stack of vSphere for my own labbing purposes
* ESXi, vCenter, vRealize Automation, NSX-T, vRealize Log Insight and more

### OPNSense

* Handles all Routing \ Firewalling


## Routing \ Firewalling

All routing and firewalling happens on OPNSense

This includes but not limited to
* GeoIP Blocking
* Blocking of certain internal devices to reach internet
* AD Blocking via DNSBL
* BGP peering to NSX-T
* DNS over TLS
* DNS blocking of all rogue DNS devices

## Networking

Internal networking is varied

* Core Cluster is 2x HPE 5900AF
* Distribution switch in attic is HPE 2530
* Primary WLAN for internal devices is 3x Linksys Velop in bridge mode with meshing
* Secondary WLAN including labbing is 3x MSM466 access points + 1x Cisco Aironet
* Media Center (main living room) is TP-Link SG108
* Office Lab is TP-Link SG108 POE
* Not use mDNS for anything that can work with regular DNS
* Wireguard implemented for all clients leaving the house

## Hardening

Hardening is done by, but not limited to 

* Only allow publickey login to servers and devices (outside of lab networks)
* All lab networks are firewalled off from production networks but can reach internet
* MFA implemented on all services that support them (using Yubikey)
* Limited number of open ports exposed online


## Logging

Multiple services and devices have implemented logging in different ways

* Network switches send syslogs to Graylog
* All docker containers send syslogs to Graylog
* All servers send syslogs to Graylog
* Cronjobs send email reports to email for every run


##Backup

Multiple methods of backups are implemented

* OPNsense backs up its config once a day and uploads it to my Nextcloud instance
* All docker containers and compose files are backed up every night (round robin between two cloud providers using rclone and crypt)
* All personal files are backed up twice a week (round robin between two cloud providers using rclone and crypt)
* TODO - Switch config automatic backup

## Acknowledgments

Inspiration, Collaboration

* Mstone
* Tinkerer
* Tediore
* Skalavala
* Pdobrian
* Ndonegan
