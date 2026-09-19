
# Week 3 – Identify Packet Flow

## Overview

- I learned how packets travel in LAN and WAN networks.
- I used Simulation mode to check the DNS and HTTP packet flow.
- I removed some network links and checked how the packet path changed.
- I used tracert to check the path from one device to another.
- I compared the tracert results with the HTTP packet flow in Packet Tracer.

---

## Task 1 – Verify Connectivity

I first tested connectivity from PC0 using the Web Browser.

I accessed:

- `www.cisco.pka`
- `www.web.pka`

Both websites loaded successfully, confirming that PC0 could communicate with the remote networks.

---

## Task 2 – Remote LAN Network Topology

### DNS Packet Path Prediction

Before forwarding the packets in Simulation mode, I predicted that PC0 would send the DNS request through the home network and then across the network to the Public DNS server.

After observing the simulation, the DNS request travelled through:

**PC0 → Wireless Router0 → Cable Modem0 → Cloud0 → Router5 → East → Switch0 → Switch1 → Public DNS**

The DNS response then travelled back towards PC0.

### HTTP Packet Path

After the IP address of `www.web.pka` was resolved, I observed the HTTP packets in Simulation mode.

The HTTP packets travelled through:

**PC0 → Wireless Router0 → Cable Modem0 → Cloud0 → Router5 → East → Switch0 → Switch1 → Switch2 → www.web.pka**

The response packets travelled back through the network to PC0.

### Broken LAN Link

I switched to Realtime mode and removed the link between **Switch0 and Switch1** in the Public Network. After allowing the network to adjust, I accessed `www.web.pka` from Tablet0 in Simulation mode.

The webpage was still accessible because another path was available.

The observed path used:

**Switch0 → Switch2 → www.web.pka**

instead of using the broken Switch0–Switch1 link.

This showed that the redundant LAN topology provided an alternative path when one link became unavailable.

---

## Task 3 – WAN Network Topology

### PC0 to www.cisco.pka

I used Simulation mode to observe communication between PC0 and `www.cisco.pka`.

### DNS Packet Path Prediction

I predicted that the DNS request would travel from PC0 through the home network and WAN to the Public DNS server so that the IP address of `www.cisco.pka` could be resolved.

The packet travelled from the home network through the WAN towards the Public DNS server and the DNS response returned to PC0.

### HTTP Packet Path

After DNS resolution, I observed the HTTP packets travelling towards `www.cisco.pka`.

Before the WAN link was removed, the main WAN path observed was:

**PC0 → Wireless Router0 → Cable Modem0 → Cloud0 → Router5 → Router2 → Router4 → West → Switch → www.cisco.pka**

The response travelled back towards PC0.

### Broken WAN Link

I switched to Realtime mode and removed the link between **Router4 and Router2**.

The routers were using EIGRP, so the routing path adjusted after the direct connection became unavailable.

I then accessed `www.cisco.pka` from Tablet0 in Simulation mode.

The alternative WAN path observed was:

**Tablet0 → Wireless Router0 → Cable Modem0 → Cloud0 → Router5 → Router2 → Router3 → Router4 → West → Switch → www.cisco.pka**

The packets used **Router3** as an alternative route between Router2 and Router4.

This showed how dynamic routing can redirect traffic when a WAN link becomes unavailable.

---

## Task 4 – PC1 to www.web.pka

### Traceroute

From PC1, I opened Command Prompt and ran:

`tracert www.web.pka`

The traceroute showed the Layer 3 hops between PC1 and the destination.

| Trace Number | Device | Interface | IP Address |
|---:|---|---|---|
| 1 | West | GigabitEthernet0/1 | `192.168.0.1` |
| 2 | Router4 | Serial0/1/1 | `209.165.200.225` |
| 3 | Router3 | Serial0/0/0 | `192.0.2.2` |
| 4 | Router2 | Serial0/0/1 | `192.0.2.18` |
| 5 | Router5 | Serial0/1/1 | `192.0.2.26` |
| 6 | East | Serial0/0/0 | `209.165.202.130` |
| 7 | www.web.pka | NIC | `209.165.202.132 / 192.168.2.254` |

### Network Address Translation

The activity uses NAT for the `www.web.pka` server.

The server has the private IP address:

`192.168.2.254`

and it is represented externally using the routable address:

`209.165.202.132`

This allows the private web server to be accessed across the network using a routable IPv4 address.

### Comparing Tracert and HTTP Simulation

I then opened `www.web.pka` from PC1 in Simulation mode and followed the HTTP packets using Capture/Forward.

The main HTTP path observed was:

**PC1 → Switch → West → Router4 → Router3 → Router2 → Router5 → East → Switch0 → Switch1 → Switch2 → www.web.pka**

The `tracert` results and HTTP simulation showed the same main Layer 3 route through:

**West → Router4 → Router3 → Router2 → Router5 → East**

The difference was that Packet Tracer Simulation mode also showed the switches and other devices used to forward the HTTP packets, while `tracert` mainly showed the Layer 3 hops between PC1 and the destination.

---

## Evidence

### Figure 1 – Connectivity Test

![Connectivity Test](images/week3-connectivity-test.png)

*Figure 1: Successful access to the web server from the home network.*

### Figure 2 – DNS and HTTP Packet Flow

![DNS and HTTP Packet Flow](images/week3-dns-http-packet-flow.png)

*Figure 2: DNS and HTTP packets observed using Packet Tracer Simulation mode.*

### Figure 3 – LAN Alternative Path

![LAN Alternative Path](images/week3-broken-lan-alternative-path.png)

*Figure 3: Packet flow after removing the link between Switch0 and Switch1.*

### Figure 4 – WAN Packet Flow

![WAN Packet Flow](images/week3-wan-http-path.png)

*Figure 4: HTTP packet flow across the WAN.*

### Figure 5 – WAN Alternative Path

![WAN Alternative Path](images/week3-broken-wan-alternative-path.png)

*Figure 5: Alternative WAN packet path after removing the Router4–Router2 link.*

### Figure 6 – PC1 Traceroute

![PC1 Traceroute](images/week3-task1-pc1-tracert-web.png)

*Figure 6: Traceroute from PC1 to www.web.pka showing the Layer 3 hops.*

### Figure 7 – PC1 HTTP Simulation

![PC1 HTTP Packet Path](images/week3-task1-pc1-http-packet-path.png)

*Figure 7: HTTP packet path from PC1 to www.web.pka in Simulation mode.*

---

## Reflection

- This activity helped me understand more clearly how packet flow works in LAN and WAN networks and how data travels from a source device to a destination.
- By using Simulation mode, I was able to follow the packets step by step instead of only seeing the final result.
- I observed that DNS communication happens before HTTP communication because the website name first needs to be resolved to an IP address.
- I was able to see how packets travel through different network devices such as switches and routers before reaching the destination server.
- By removing the link between Switch0 and Switch1, I learned that the LAN could still use another available path to reach the web server.
- I also removed the link between Router4 and Router2 and observed how EIGRP selected an alternative route through Router3, allowing the communication to continue.
- This helped me understand why having alternative paths and dynamic routing is useful when a network link becomes unavailable.
- Using tracert helped me identify the Layer 3 hops between PC1 and the web server and understand which routers were involved in the path.
- Finally, comparing the tracert results with Simulation mode helped me understand that tracert mainly shows the Layer 3 hops, while Packet Tracer Simulation provides more detail about how packets move through the network.
