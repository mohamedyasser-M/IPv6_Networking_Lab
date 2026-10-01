# IPv6 Networking Lab

This is a simple IPv6 network made in Cisco Packet Tracer.

The network has two LANs connected using a router.

## Topology

PC1 ── SW1 ── Router ── SW2 ── PC3  
PC2 ── SW1              SW2 ── PC4

### Devices

- 1 Router
- 2 Switches
- 4 PCs

## IPv6 Addressing

There are two IPv6 networks in this lab.

### LAN 1

- Network: 2001:DB8:1:1::/64
- Router G0/0: 2001:DB8:1:1::1
- PC1: 2001:DB8:1:1::10
- PC2: 2001:DB8:1:1::20
- Gateway: 2001:DB8:1:1::1

### LAN 2

- Network: 2001:DB8:1:2::/64
- Router G0/1: 2001:DB8:1:2::1
- PC3: 2001:DB8:1:2::10
- PC4: 2001:DB8:1:2::11
- Gateway: 2001:DB8:1:2::1

## Router Configuration

IPv6 routing was enabled on the router using:

ipv6 unicast-routing

The router has two IPv6 interfaces:

G0/0 → 2001:DB8:1:1::1/64  
G0/1 → 2001:DB8:1:2::1/64

## Routing

The router automatically knows both networks because they are directly connected.

C 2001:DB8:1:1::/64  
C 2001:DB8:1:2::/64

C means Connected.

The router also has local routes for its own IPv6 addresses.

L 2001:DB8:1:1::1/128  
L 2001:DB8:1:2::1/128

L means Local.

## NDP

IPv6 uses NDP to find the MAC address of a device on the local network.

When a device wants to communicate with a device on another network, it uses NDP to find the MAC address of the default gateway.

## Testing

The network was tested using ping.

PC1 was able to ping PC2 on the same LAN.

PC3 was able to ping PC4 on the same LAN.

PC1 was also able to ping PC3 on the other LAN.

This shows that IPv6 routing between the two networks is working.

## Files

- Packet-Tracer/ → Packet Tracer project
- Configs/ → Router and switch configurations
- Screenshots/ → Project screenshots