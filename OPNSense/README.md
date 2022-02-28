## GeoIP blocking

GeoIP blocking is implemented using MaxMind GeoIP API.
Since I'm only interested in access from Norwegian IPs I've made an alias that only lists NO addresses, then a WAN firewall rule that uses the negate of said alias will be blocked !GeoIPNorway


## Blocking of specific devices from reaching the internet

Instead of using a cumbersome way of isolating non trusted devices that breaks (sometimes unfortunately needed) mDNS and other local discovery technologies I have an alias defined that contains any "less" trusted devices on my local network, including cheap POE cameras and cloud based bulbs with local control.
This alias is then placed on the LAN interface and blocks any traffic from said devices from exiting the LAN interface

## Advertisement \ cookie blocking on a network wide level

I tried playing around with Pihole and Adguard, however it makes very little sense to do this on an outside device when OPNsense is already my DNS server
