# Sonos SSDP Proxy

Queries Sonos devices on one VLAN/subnet, caches these answers, and then answers queries on one or more other
VLANs/subnets.

Running this script will allow you to reliably get Sonos working across VLANs. Remember to open the necessary ports
on your firewall for regular Sonos communication.

## Requirements

- Linux box with access to all desired subnets (e.g. pfSense or a VM)
- Python2
- netifaces for Python

## Use

    ./sonos-ssdp-proxy eth0 eth1 eth2

The first specified interface is on the subnet with the Sonos devices; the later interfaces are query interfaces. For
example, eth1 might be a client network, and eth2 a guest network.

You can also specify `-v` for debugging info, and `--controller [...]` with an existing controller ID to use when
querying Sonos devices, although this seems to make no difference at the moment.

## Todo

- This could easily be generalized to things other than just Sonos
- Listening on multiple interfaces is buggy
- The code would be easier to understand if broken into more classes/functions

I'm not planning to maintain this except as needed for my own use, but pull requests are welcome.
