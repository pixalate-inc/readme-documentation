---
title: "IPv6 Types"
excerpt: ""
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

Prefix | Designation and Explanation  | IPv4 Equivalent  
---|---|---  
**::/128** |  **Unspecified** This address may only be used as a source address by an initialising host before it has learned its own address. | 0.0.0.0  
**::1/128** |  **Loopback** This address is used when a host talks to itself over IPv6. This often happens when one program sends data to another. | 127.0.0.1  
**::ffff/96** _Example:_ _::ffff:192.0.2.47_ |  **IPv4-Mapped** These addresses are used to embed IPv4 addresses in an IPv6 address. One use for this is in a dual stack transition scenario where IPv4 addresses can be mapped into an IPv6 address. See RFC 4038 for more details. | There is no equivalent. However, the mapped IPv4 address can be looked up in the relevant RIR's Whois database.  
**fc00::/7** _Example:_ _fdf8:f53b:82e4::53_ |  **Unique Local Addresses (ULAs)** These addresses are reserved for local use in home and enterprise environments and are not public address space. These addresses might not be unique, and there is no formal address registration. Packets with these addresses in the source or destination fields are not intended to be routed on the public Internet but are intended to be routed within the enterprise or organisation. See RFC 4193 for more details. |  Private, or RFC 1918 address space: 10.0.0.0/8 172.16.0.0/12 192.168.0.0/16  
**fe80::/10** _Example:_ _fe80::200:5aee:feaa:20a2_ |  **Link-Local Addresses** These addresses are used on a single link or a non-routed common access network, such as an Ethernet LAN. They do not need to be unique outside of that link. Link-local addresses may appear as the source or destination of an IPv6 packet. Routers must not forward IPv6 packets if the source or destination contains a linklocal address. Link-local addresses may appear as the source or destination of an IPv6 packet. Routers must not forward IPv6 packets if the source or destination contains a link-local address. | 169.254.0.0/16  
**2001:0000::/32** _Example:_ _2001:0000:4136:e378:_ _8000:63bf:3fff:fdd2_ |  **Teredo** This is a mapped address allowing IPv6 tunneling through IPv4 NATs. The address is formed using the Teredo prefix, the server’s unique IPv4 address, flags describing the type of NAT, the obfuscated client port and the client IPv4 address, which is probably a private address. It is possible to reverse the process and identify the IPv4 address of the relay server, which can then be looked up in the relevant RIR’s Whois database.  | No equivalent  
**2001:0002::/48** _Example:_ _2001:0002:6c::430_ |  **Benchmarking** These addresses are reserved for use in documentation. They should not be used as source or destination addresses. | 198.18.0.0/15  
**2001:0010::/28** _Example:_ _2001:10:240:ab::a_ |  **Orchid** These addresses are used for a fixed-term experiment. They should only be visible on an end-to-end basis and routers should not see packets using them as source or destination addresses. | No equivalent  
**2002::/16** _Example:_ _2002:cb0a:3cdd:1::1_ |  **6to4** A 6to4 gateway adds its IPv4 address to this 2002::/16, creating a unique /48 prefix. As the IPv4 address of the gateway router is used to compose the IPv6 prefix, it is possible to reverse the process and identify the IPv4 address, which can then be looked up in the relevant RIR’s Whois database. | There is no equivalent but 192.88.99.0/24 has been reserved as the 6to4 relay anycase address prefix by the IETF.  
**2001:db8::/32** _Example:_ _2001:db8:8:4::2_ |  **Documentation** These addresses are used in examples and documentation. They should never be source or destination addresses. |  192.0.2.0/24 198.51.100.0/24 203.0.113.0/24  
**2000::/3** |  **Global Unicast** These addresses are globally unique. They are routable IP addresses used by individual devices. The operators of networks using these addresses can be found using the Whois servers of the RIRs listed in the registry at: <http://www.iana.org/assignments/ipv6-unicast-address-assignments> | No equivalent single block.  
**ff00::/8** _Example:_ _ff01:0:0:0:0:0:0:2_ |  **Multicast** These addresses are used to identify multicast groups. They should only be used as destination addresses, never as source addresses. | 224.0.0.0/4
