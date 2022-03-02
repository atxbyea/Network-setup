## GeoIP blocking

GeoIP blocking is implemented using MaxMind GeoIP API.
Since I'm only interested in access from Norwegian IPs I've made an alias that only lists NO addresses, then a WAN firewall rule that uses the negate of said alias will be blocked !GeoIPNorway


## Blocking of specific devices from reaching the internet

Instead of using a cumbersome way of isolating non trusted devices that breaks (sometimes unfortunately needed) mDNS and other local discovery technologies I have an alias defined that contains any "less" trusted devices on my local network, including cheap POE cameras and cloud based bulbs with local control.
This alias is then placed on the LAN interface and blocks any traffic from said devices from exiting the LAN interface

## Advertisement \ cookie blocking on a network wide level

I tried playing around with Pihole and Adguard, however it makes very little sense to do this on an outside device when OPNsense is already my DNS server
This is implemented using DNSBL under Unbound DNS

## BGP Peering with NSX-T

This is a side project I have while learning NSX-T, I passed the VCP-NV 2021 in December 2021 and have been playing more and more with NSX when I have time awaiting more customer implementations

## DNS over TLS (DoT)

Opnsense supports DoT natively, and since I'm already using Cloudflare for my domain services it makes sense to use Cloudflares DoT service

## Blocking rogue DNS clients

A lot of consumer hardware (TVs, cloud based hardware, streaming boxes etc) use hard coded DNS server even if they get a DNS server from their DHCP lease
Since a lot of these devices can then be pushing tracking cookies \ advertising even though the DNSBL is implemented as above we want to avoid this.
This is accomplished by blocking all outgoing DoT traffic from client networks, and redirecting all outgoing port 53 requests to OPNsense itself.
