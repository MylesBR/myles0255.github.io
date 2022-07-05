---
title: Configure Static IP in Linux 
date: 2022-06-15
categories: [Networking, Servers] 
tags: [network,server,linux]            # TAG names should always be be lowercase and seperated by a commma
---

# Configure Static IP Address in Debian

Open in your favorite text editor the file `/etc/network/interfaces`

```bash
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
allow-hotplug ens18
iface ens18 inet dhcp
```

Update the line `iface ens18 inet dhcp` like


```bash
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
allow-hotplug ens18
iface ens18 inet static
 address IP-Address
 netmask NETMASK
 gateway Gateway IP
 dns-domain domain-name
 dns-nameservers dnsserver
```
