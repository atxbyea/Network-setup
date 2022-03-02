## Public Key authentication on all devices

Currently pubkey is implemented on all my devices, and for switches it is implemented as a primary login method whereas for linux servers it is the only option for login

## Networks firewalled off from eachother

All networks are by default "deny all" and opened on a per port \ source - destination basis
However all networks have full access to the internet except the IoT network (rarely used to isolate clients for packet inspection)

## MFA \ Yubikey

Services that are internet exposed all require either MFA or Yubikey (preferred) for authentication
Yubikeys are also used as MFA for any internet services I use where possible, if not TOTP via Authy is implemented.

## Limiting attack vectors

By default one should only expose needed ports online, using reverse proxies and other smart techniques you can route a lot of traffic through obscure port or over for example HTTPS 
With GeoIP blocking you are already limiting the number of vectors, exposing a single port online and logging all traffic on said port will be very easy to monitor and maintain
