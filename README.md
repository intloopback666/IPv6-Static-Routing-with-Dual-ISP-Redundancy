# IPv6-Static-Routing-with-Dual-ISP-Redundancy

The objective of this lab is to:
Configure IPv6 addressing on routers and interfaces.
Enable IPv6 packet forwarding using ipv6 unicast-routing.
Configure static routes between internal IPv6 networks.
Use IPv6 link-local addresses as static-route next hops.
Configure a primary and backup default route.
Verify IPv6 routing-table entries and connectivity.

Expected Result
All internal IPv6 networks should communicate successfully, with R1 forwarding external traffic through ISP1. ISP2 will be used as a backup if the primary default route through ISP1 becomes unavailable.

IPv6 Addressing:
R1 E0/0  : 2001:DB8:1111:1::1/64
R1 S1/1  : 2001:DB8:1111:12::1/64
R1 S1/2  : 2001:DB8:1111:13::1/64
R1 E0/1  : 2001:DB8:1111:15::1/64
R1 E0/2  : 2001:DB8:1111:16::1/64
R2 E0/0  : 2001:DB8:1111:2::1/64
R2 S1/1  : 2001:DB8:1111:12::2/64
R3 E0/0  : 2001:DB8:1111:3::1/64
R3 S1/2  : 2001:DB8:1111:13::2/64
R4 E0/0  : 2001:DB8:1111:4::1/64
R4 S1/3  : IPv6 link-local address
ISP1 E0/1: 2001:DB8:1111:15::2/64
ISP1 Lo0  : 2001:4860:4860::8888/128
ISP2 E0/2: 2001:DB8:1111:16::2/64
ISP2 Lo0  : 2001:4860:4860::8888/128

Verification Commands:
show ipv6 interface brief
show ipv6 route
show ipv6 route static
ping ipv6 2001:4860:4860::8888
traceroute ipv6 2001:4860:4860::8888
