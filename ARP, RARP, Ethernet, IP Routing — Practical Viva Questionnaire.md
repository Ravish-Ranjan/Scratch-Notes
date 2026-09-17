# ARP, RARP, Ethernet, IP Routing — Practical Viva Questionnaire

This questionnaire is based on the uploaded practical program `a3.py`, which simulates an Ethernet LAN, ARP, RARP, ARP caching/expiry, IP packet delivery, routing between two subnets, and TTL handling. The program defines separate structures for Ethernet frames, IP packets, ARP requests/replies, RARP requests/replies, hosts, router interfaces, a router, an ARP cache, and a RARP server.

---

## 1. Basic Networking Concepts

### Q1. What is a computer network?

**Answer:** A computer network is a collection of interconnected devices that communicate and exchange data using communication protocols.

### Q2. What is a LAN?

**Answer:** LAN stands for **Local Area Network**. It connects devices within a limited geographical area such as a home, laboratory, office, or campus network.

### Q3. What is a subnet?

**Answer:** A subnet is a logically divided portion of an IP network. It determines which IP addresses are considered local to a particular network.

### Q4. What is a broadcast domain?

**Answer:** A broadcast domain is a network area in which a broadcast frame can reach all attached devices. The practical models each `Network` object as one Ethernet LAN/broadcast domain. fileciteturn0file0L86-L102

### Q5. What is an IP address?

**Answer:** An IP address logically identifies a network interface at the network layer and is used for IP communication and routing.

### Q6. What is a MAC address?

**Answer:** A MAC address is a link-layer hardware address used to identify an interface on an Ethernet network.

### Q7. What is the difference between IP address and MAC address?

**Answer:**

- **IP address:** Logical, network-layer address; used for IP communication and routing.
- **MAC address:** Link-layer address; used for delivery of Ethernet frames on the local network.

### Q8. What is Ethernet?

**Answer:** Ethernet is a family of LAN technologies that uses frames and MAC addresses for communication at the data-link layer.

### Q9. Which OSI layer is Ethernet primarily associated with?

**Answer:** **Data Link Layer (Layer 2)**, although Ethernet also defines physical-layer aspects.

### Q10. Which OSI layer does IP belong to?

**Answer:** **Network Layer (Layer 3).**

---

# 2. ARP

### Q11. What is ARP?

**Answer:** ARP stands for **Address Resolution Protocol**. It resolves an IPv4 address to the corresponding MAC address on a local network.

### Q12. Why is ARP required?

**Answer:** IP communication uses IP addresses, but Ethernet delivery requires a destination MAC address. ARP obtains the MAC address associated with a local IPv4 address.

### Q13. What is the basic ARP process?

**Answer:**

1. Check the ARP cache.
2. If the mapping is missing, broadcast an ARP Request.
3. The device owning the target IP responds with an ARP Reply.
4. The sender stores the IP-to-MAC mapping in its ARP cache.
5. The sender can then construct the Ethernet frame.

The practical implements this flow in `resolve_arp()`. fileciteturn0file0L225-L264

### Q14. What does an ARP Request ask?

**Answer:** It effectively asks: **"Who has this IP address?"**

The program stores the requested address in `target_ip`. fileciteturn0file0L241-L253

### Q15. Is an ARP Request broadcast or unicast?

**Answer:** An ARP Request is normally **broadcast** on the local Ethernet network.

The practical uses `FF:FF:FF:FF:FF:FF` as the destination MAC. fileciteturn0file0L247-L253

### Q16. What is the Ethernet broadcast MAC address?

**Answer:** `FF:FF:FF:FF:FF:FF`.

### Q17. Is an ARP Reply normally broadcast?

**Answer:** Normally, the ARP Reply is **unicast** to the requester.

The practical explicitly creates a reply frame whose destination MAC is the original requester's MAC. fileciteturn0file0L280-L296

### Q18. What happens when a host receives an ARP Request?

**Answer:** It checks whether the requested IP matches its own IP. If it does not, it ignores the request. If it does, it sends an ARP Reply containing its IP-to-MAC mapping. fileciteturn0file0L266-L296

### Q19. What happens if no device owns the requested IP?

**Answer:** No ARP Reply is generated, so the sender cannot resolve the destination MAC. The practical reports ARP failure and does not send the IP packet. fileciteturn0file0L255-L264

### Q20. What is an ARP cache?

**Answer:** An ARP cache stores recently learned IP-to-MAC mappings so that ARP broadcasts do not have to be performed for every packet.

### Q21. Why is ARP caching useful?

**Answer:** It reduces unnecessary ARP broadcasts and makes repeated communication faster.

### Q22. What does an ARP cache HIT mean?

**Answer:** It means the requested IP-to-MAC mapping exists in the cache and has not expired.

### Q23. What does an ARP cache MISS mean?

**Answer:** It means the requested mapping is not currently available in the cache, so ARP resolution is required.

### Q24. What happens when an ARP cache entry expires?

**Answer:** The entry is deleted and a subsequent lookup becomes a cache MISS. The practical uses `time.monotonic()` to determine expiry. fileciteturn0file0L22-L43

### Q25. What is TTL in the ARP cache in this practical?

**Answer:** It is the amount of time for which a cached IP-to-MAC mapping remains valid. Host-A and the other hosts are configured with an ARP TTL of **5 seconds**. fileciteturn0file0L599-L624

### Q26. Why does the practical wait for 6 seconds?

**Answer:** The cache TTL is 5 seconds, so waiting 6 seconds demonstrates that the cached mapping has expired and must be resolved again. fileciteturn0file0L691-L699

---

# 3. RARP

### Q27. What is RARP?

**Answer:** RARP stands for **Reverse Address Resolution Protocol**. It was designed to allow a device that knows its MAC address to obtain its IP address from a RARP server.

### Q28. How is RARP different from ARP?

**Answer:**


| ARP                                  | RARP                                     |
| ------------------------------------ | ---------------------------------------- |
| IP → MAC                             | MAC → IP                                 |
| Used to find a MAC address for an IP | Used to obtain an IP address using a MAC |
| Common in IPv4 local networks        | Largely obsolete in modern networks      |


### Q29. What information does the host know before RARP in this practical?

**Answer:** The host knows only its MAC address. The program explicitly demonstrates this situation before sending the RARP Request. fileciteturn0file0L196-L213

### Q30. Is the RARP Request broadcast in this simulation?

**Answer:** Yes. The RARP Request is placed inside an Ethernet broadcast frame. fileciteturn0file0L202-L213

### Q31. What does the RARP server maintain?

**Answer:** It maintains a static **MAC-to-IP mapping**. fileciteturn0file0L130-L140

### Q32. What happens when the RARP server finds a mapping?

**Answer:** It creates an RARP Reply containing the assigned IP address and sends it as a unicast Ethernet frame to the requesting MAC address. fileciteturn0file0L148-L174

### Q33. What happens if the RARP server does not know the MAC address?

**Answer:** No RARP Reply is sent. The practical demonstrates this with `Unknown-Host`. fileciteturn0file0L664-L673

### Q34. Why is RARP largely obsolete?

**Answer:** Modern mechanisms such as **BOOTP** and especially **DHCP** provide more complete IP configuration, including IP address, subnet mask, gateway, DNS information, and other options.

### Q35. Can RARP provide a complete network configuration?

**Answer:** No. RARP's basic purpose is to obtain an IP address from a MAC address. It does not provide the broad configuration capabilities of DHCP.

---

# 4. Ethernet Frames

### Q36. What is an Ethernet frame?

**Answer:** An Ethernet frame is a Layer-2 data unit used to carry data across an Ethernet network.

### Q37. What fields are represented by `EthernetFrame` in this practical?

**Answer:** The simulation represents:

- Source MAC
- Destination MAC
- Payload

This is represented by the `EthernetFrame` dataclass. fileciteturn0file0L50-L54

### Q38. What is the payload of an Ethernet frame?

**Answer:** The payload is the higher-layer data carried by the Ethernet frame. In this practical it may contain an ARP message, RARP message, or IP packet.

### Q39. What happens to a broadcast frame in the simulated network?

**Answer:** It is delivered to every device attached to that network. fileciteturn0file0L109-L118

### Q40. What happens to a unicast frame?

**Answer:** The simulation searches for the device whose MAC address matches the destination MAC and delivers the frame only to that device. fileciteturn0file0L121-L128

### Q41. What happens if no device owns the destination MAC?

**Answer:** The Ethernet frame is dropped. fileciteturn0file0L121-L128

---

# 5. IP Packets

### Q42. What is an IP packet?

**Answer:** An IP packet is a Layer-3 data unit used to carry data from a source IP address to a destination IP address.

### Q43. What fields does `IPPacket` contain in this simulation?

**Answer:**

- Source IP
- Destination IP
- TTL
- Data

The corresponding dataclass is defined in the practical. fileciteturn0file0L56-L61

### Q44. What is the difference between an IP packet and an Ethernet frame?

**Answer:** An IP packet is a Layer-3 unit, while an Ethernet frame is a Layer-2 unit that carries the IP packet.

### Q45. Does the IP source/destination change when a router forwards the packet in this simulation?

**Answer:** No. The practical explicitly keeps the IP source and destination unchanged while creating a new Ethernet frame for the outbound LAN. fileciteturn0file0L504-L518

### Q46. Do the Ethernet MAC addresses change when a router forwards a packet?

**Answer:** Yes. The router creates a new Ethernet frame using the outbound interface's MAC address as the source and the next destination's MAC address as the destination. fileciteturn0file0L504-L518

---

# 6. Same-Subnet Communication

### Q47. How does a host determine whether a destination is local?

**Answer:** It checks whether the destination IP belongs to its configured subnet.

The practical performs this test using the Python `ipaddress` module. fileciteturn0file0L322-L333

### Q48. Does a router need to be used for communication between two hosts on the same subnet?

**Answer:** Normally, no. The sender resolves the destination host's MAC address using ARP and sends the Ethernet frame directly to that MAC.

The practical explicitly prints that a router is not required for local-subnet communication. fileciteturn0file0L324-L328

### Q49. What happens in Host-A → Host-B communication?

**Answer:**

1. Host-A checks its ARP cache.
2. If there is no valid mapping, Host-A broadcasts an ARP Request.
3. Host-B recognizes that the requested IP belongs to it.
4. Host-B sends an ARP Reply.
5. Host-A caches Host-B's MAC.
6. Host-A creates an IP packet.
7. Host-A encapsulates it in an Ethernet frame addressed to Host-B.
8. Host-B receives the packet.

### Q50. Why does Host-A not use the gateway for Host-B?

**Answer:** Host-B belongs to Host-A's local subnet, so Host-A can communicate directly with Host-B at Layer 2.

---

# 7. Default Gateway

### Q51. What is a default gateway?

**Answer:** A default gateway is the router interface used to reach destinations that are outside the host's local subnet.

### Q52. When does the host use its gateway in this practical?

**Answer:** When the destination IP is not inside the host's local subnet. The next-hop IP is then set to the configured gateway IP. fileciteturn0file0L324-L336

### Q53. Why does the sender ARP for the gateway rather than the remote host?

**Answer:** ARP operates on the local LAN. A remote host is not directly reachable at Layer 2, so the sender needs the MAC address of the local router interface, which becomes the next hop.

### Q54. If Host-A wants to reach Host-C, whose MAC address does Host-A need?

**Answer:** Host-A needs the MAC address of the router's LAN-1 interface, not Host-C's MAC address.

---

# 8. Router

### Q55. What is the purpose of a router?

**Answer:** A router connects different IP networks and forwards packets between them.

### Q56. How many interfaces does the router have in this practical?

**Answer:** Two:

- `R1-LAN1`
- `R1-LAN2`

They connect LAN-1 and LAN-2 respectively. fileciteturn0file0L636-L650

### Q57. What are the router's IP addresses?

**Answer:**

- LAN-1 interface: `192.168.1.1`
- LAN-2 interface: `192.168.2.1`

These are configured in the practical. fileciteturn0file0L638-L650

### Q58. What are the two simulated networks?

**Answer:**

- LAN-1: `192.168.1.0/24`
- LAN-2: `192.168.2.0/24`

fileciteturn0file0L579-L590

### Q59. What IP addresses do Host-A, Host-B and Host-C have?

**Answer:**

- Host-A: `192.168.1.10`
- Host-B: `192.168.1.20`
- Host-C: `192.168.2.10`

fileciteturn0file0L599-L624

### Q60. Which hosts are on the same subnet?

**Answer:** Host-A and Host-B are on `192.168.1.0/24`. Host-C is on `192.168.2.0/24`.

### Q61. What is the router's job in Host-A → Host-C communication?

**Answer:** The router receives the IP packet from LAN-1, determines that Host-C belongs to LAN-2, decrements TTL, resolves Host-C's MAC on LAN-2, creates a new Ethernet frame, and transmits it onto LAN-2. fileciteturn0file0L463-L519

### Q62. How does the router determine its outbound interface?

**Answer:** It checks its interfaces and selects the interface whose subnet contains the destination IP. fileciteturn0file0L456-L460

### Q63. What happens if the router cannot find a route to the destination?

**Answer:** The simulation drops the packet and reports that there is no route for the destination IP. fileciteturn0file0L482-L486

---

# 9. Cross-Subnet Communication

### Q64. Explain Host-A → Host-C communication step by step.

**Answer:**

```text
Host-A
  |
  | ARP for gateway 192.168.1.1
  v
R1-LAN1
  |
  | Router forwards IP packet
  | TTL decreases
  v
R1-LAN2
  |
  | ARP for Host-C
  v
Host-C
```

The practical models this as a packet from `192.168.1.10` to `192.168.2.10`. fileciteturn0file0L711-L715

### Q65. What happens to the destination IP while crossing the router?

**Answer:** It remains the final destination IP, `192.168.2.10`, in this simulation.

### Q66. What happens to the Ethernet destination MAC at the router?

**Answer:** It changes for the next LAN. On LAN-1 the frame is addressed to the router's LAN-1 MAC; on LAN-2 the new frame is addressed to Host-C's MAC.

### Q67. Why does the router need ARP on the outbound LAN?

**Answer:** The router knows the destination IP but needs the destination MAC to create the Ethernet frame on the outgoing LAN.

### Q68. Can the router simply forward the original Ethernet frame unchanged?

**Answer:** No. The Ethernet frame is valid only for the local link. The router creates a new Ethernet frame for the next link.

---

# 10. TTL — Time To Live

### Q69. What is TTL?

**Answer:** TTL stands for **Time To Live**. In IPv4, it is a field used to limit how many router hops a packet can make.

### Q70. Why is TTL necessary?

**Answer:** It prevents packets from circulating indefinitely in routing loops.

### Q71. What does the router do to TTL?

**Answer:** It decrements TTL by 1 when forwarding the packet. The practical performs `packet.ttl -= 1`. fileciteturn0file0L463-L480

### Q72. What happens if TTL becomes zero?

**Answer:** The packet is dropped because its TTL has expired. fileciteturn0file0L474-L480

### Q73. What happens in the TTL demonstration with `TTL=1`?

**Answer:** Host-A sends a packet with TTL 1 to Host-C. The router decrements it to 0 and drops the packet. fileciteturn0file0L727-L733

### Q74. Does a normal Layer-2 switch decrement IP TTL?

**Answer:** No. TTL is handled by Layer-3 routing devices such as routers.

---

# 11. OSI and TCP/IP Layer Questions

### Q75. Which layer does ARP operate between?

**Answer:** ARP is commonly described as a protocol that operates between Layer 2 and Layer 3 because it maps an IPv4 network-layer address to a MAC link-layer address.

### Q76. Which layer handles MAC addresses?

**Answer:** Data Link Layer (Layer 2).

### Q77. Which layer handles IP addresses?

**Answer:** Network Layer (Layer 3).

### Q78. Which layer is responsible for routing?

**Answer:** Network Layer (Layer 3).

### Q79. Which device primarily operates at Layer 2?

**Answer:** A traditional Ethernet switch.

### Q80. Which device primarily operates at Layer 3?

**Answer:** A router.

### Q81. Does a router operate only at Layer 3?

**Answer:** A router makes forwarding decisions at Layer 3, but its interfaces also necessarily participate in lower-layer technologies such as Ethernet.

### Q82. What is encapsulation?

**Answer:** Encapsulation is the process of placing higher-layer data inside a lower-layer protocol unit.

For example:

```text
Application data
      ↓
     IP packet
      ↓
 Ethernet frame
```

### Q83. What is decapsulation?

**Answer:** Decapsulation is the process of removing protocol headers as data moves upward through the protocol stack.

---

# 12. Python Implementation Questions

### Q84. Why is `@dataclass` used?

**Answer:** It provides a convenient way to define classes primarily used to store structured data, such as `IPPacket`, `EthernetFrame`, `ARPRequest`, and `ARPReply`. fileciteturn0file0L10-L84

### Q85. Why is the `ipaddress` module used?

**Answer:** It is used to represent IP networks and determine whether an IP address belongs to a particular subnet.

### Q86. Why is `time.monotonic()` used for ARP expiry?

**Answer:** It provides a steadily increasing clock suitable for measuring elapsed time, avoiding problems caused by changes to the system wall clock. The cache stores `expires_at` using this clock. fileciteturn0file0L22-L43

### Q87. What is a dictionary used for in `ARPCache`?

**Answer:** `self.entries` stores IP-to-ARP-cache-entry mappings, allowing fast lookup by IP address.

### Q88. What is stored in `ARPCacheEntry`?

**Answer:**

- IP address
- MAC address
- Expiration time

fileciteturn0file0L10-L15

### Q89. What does `Network.connect()` do?

**Answer:** It attaches a device to the network and assigns that network object to the device's `network` attribute. fileciteturn0file0L100-L104

### Q90. What does `Network.is_local()` do?

**Answer:** It checks whether a supplied IP address belongs to the network represented by that `Network` object. fileciteturn0file0L106-L107

### Q91. What is polymorphism used for in `receive_frame()`?

**Answer:** The same receiving mechanism handles different payload types and uses `isinstance()` to determine whether the payload is an ARP Request, ARP Reply, RARP Reply, or IP packet. fileciteturn0file0L266-L312

### Q92. Why is `payload` typed as `object`?

**Answer:** Because the simulated Ethernet frame can carry different kinds of messages, including ARP, RARP, and IP objects.

### Q93. Why is `None` used for Host-A's IP during the RARP demonstration?

**Answer:** It simulates a device that currently has no assigned IP address. fileciteturn0file0L654-L658

---

# 13. Practical-Specific Questions

### Q94. What are the main demonstrations performed by the program?

**Answer:**

1. Successful RARP resolution
2. Failed RARP resolution
3. Same-subnet communication
4. ARP cache hit
5. ARP cache expiry
6. ARP failure
7. Cross-subnet communication
8. Second cross-subnet packet
9. TTL demonstration

These are the nine numbered demonstrations in `main()`. fileciteturn0file0L654-L735

### Q95. What happens in the successful RARP demonstration?

**Answer:** Host-A's IP is temporarily set to `None`. It broadcasts a RARP Request using its MAC. The RARP server has a mapping for Host-A's MAC and returns `192.168.1.10`. fileciteturn0file0L654-L662

### Q96. What is the RARP mapping for Host-A?

**Answer:**

```text
00:00:00:00:00:01 → 192.168.1.10
```

The mapping is explicitly configured in the RARP server. fileciteturn0file0L631-L633

### Q97. What happens in the failed RARP demonstration?

**Answer:** `Unknown-Host` sends a RARP Request using MAC `00:00:00:00:99:99`. The RARP server has no mapping, so it sends no reply. fileciteturn0file0L664-L673

### Q98. What is the ARP failure test?

**Answer:** Host-A tries to send data to `192.168.1.99`. No simulated host owns that IP, so ARP cannot obtain a MAC address and the packet is not sent. fileciteturn0file0L703-L709

### Q99. Why does the second Host-A → Host-B packet not need another ARP Request?

**Answer:** The first communication stores Host-B's MAC in Host-A's ARP cache. The second packet can therefore use the cached mapping. fileciteturn0file0L683-L689

### Q100. Why does ARP happen again after cache expiry?

**Answer:** The cached mapping is no longer valid after its TTL expires, so Host-A must perform ARP resolution again. fileciteturn0file0L691-L699

---

# 14. Important "What If?" Viva Questions

### Q101. What if the destination is on the same subnet?

**Answer:** The host ARPs for the destination host's MAC and sends the Ethernet frame directly.

### Q102. What if the destination is on another subnet?

**Answer:** The host sends the Ethernet frame to the MAC address of its default gateway. The router then forwards the IP packet toward the destination network.

### Q103. What if the ARP cache already contains the required MAC?

**Answer:** No ARP broadcast is needed; the cached MAC is used.

### Q104. What if the ARP entry expires?

**Answer:** It is removed and ARP resolution is performed again when needed.

### Q105. What if no device responds to ARP?

**Answer:** The next-hop MAC cannot be resolved, so the practical drops the attempted transmission.

### Q106. What if the RARP server has no MAC-to-IP mapping?

**Answer:** The server sends no RARP Reply.

### Q107. What if TTL is 1 when the packet reaches a router?

**Answer:** The router decrements it to 0 and drops the packet in this simulation.

### Q108. What if the router has no interface whose subnet contains the destination?

**Answer:** The practical reports that there is no route and drops the packet. fileciteturn0file0L482-L486

### Q109. What if the Ethernet destination MAC does not belong to any connected device?

**Answer:** The simulated network drops the frame. fileciteturn0file0L121-L128

### Q110. What if Host-A has no IP address and tries to send an IP packet?

**Answer:** The practical checks for `self.ip is None` and refuses to send the packet. fileciteturn0file0L314-L320

---

# 15. Common Examiner Conceptual Questions

### Q111. Why does ARP use broadcasting?

**Answer:** The sender initially does not know which device owns the target IP, so it broadcasts the request across the local LAN.

### Q112. Why is the ARP Reply unicast?

**Answer:** Once the owner of the IP is known, the responder knows the requester's MAC address and can send the reply directly to it.

### Q113. Why can't ARP resolve a remote host directly?

**Answer:** ARP resolves addresses within the local Layer-2 network. For a remote IP, the host resolves the MAC address of the local next hop, normally the default gateway.

### Q114. Does a router forward MAC addresses from one LAN to another?

**Answer:** No. Ethernet MAC addressing is link-local. The router removes/replaces the Layer-2 framing and creates a new frame for the outgoing network.

### Q115. Does the router change the destination IP when forwarding?

**Answer:** No, not in ordinary routing. The destination IP remains the final destination. In this simulation, it explicitly remains unchanged. fileciteturn0file0L504-L510

### Q116. What changes at every router hop?

**Answer:** The Layer-2 Ethernet frame is replaced, and the IP TTL is decremented. In real IPv4 forwarding, other IP header fields/checksum handling also apply, but this simulation models TTL and reframing explicitly.

### Q117. Why are two different subnets used?

**Answer:** To demonstrate routing. Host-A and Host-B are on `192.168.1.0/24`, while Host-C is on `192.168.2.0/24`, forcing Host-A → Host-C traffic to cross the router.

### Q118. Why does the router have two IP addresses?

**Answer:** Each router interface belongs to a different IP subnet, so each interface has an address appropriate to its connected LAN.

### Q119. Why does the router have two MAC addresses?

**Answer:** Each Ethernet interface has its own link-layer MAC address.

### Q120. What is the difference between a switch and a router?

**Answer:**


| Switch                                       | Router                                   |
| -------------------------------------------- | ---------------------------------------- |
| Primarily Layer 2                            | Primarily Layer 3                        |
| Uses MAC addresses                           | Uses IP addresses for routing            |
| Connects devices within/between LAN segments | Connects different IP networks           |
| Forwards Ethernet frames                     | Forwards IP packets                      |
| Does not normally decrement IP TTL           | Decrements TTL when routing IPv4 packets |


---

# 16. ARP Cache and Routing — Deeper Questions

### Q121. Why does the first same-subnet packet require ARP but the second may not?

**Answer:** The first packet needs an IP-to-MAC mapping. Once learned, the mapping is cached and reused until it expires.

### Q122. Why does the first cross-subnet packet require ARP?

**Answer:** Host-A must resolve the MAC address of its default gateway on LAN-1. The router must then resolve Host-C's MAC on LAN-2.

### Q123. Why can the second cross-subnet packet require less ARP activity?

**Answer:** If the relevant mappings are still cached, they can be reused rather than resolved again.

### Q124. What is a next hop?

**Answer:** The next hop is the immediate device/interface to which a packet is sent on its way to its final destination.

### Q125. In Host-A → Host-C communication, what is the first next hop?

**Answer:** The router's LAN-1 interface at `192.168.1.1`.

### Q126. What is the next hop on the second LAN?

**Answer:** Host-C itself, because it is directly connected to LAN-2.

---

# 17. Addressing and Subnet Questions

### Q127. What does `/24` mean in `192.168.1.0/24`?

**Answer:** It means the first 24 bits are the network prefix, leaving 8 bits for host addresses.

### Q128. What is the typical subnet mask for `/24`?

**Answer:** `255.255.255.0`.

### Q129. What is the network address of `192.168.1.0/24`?

**Answer:** `192.168.1.0`.

### Q130. What is the network address of `192.168.2.0/24`?

**Answer:** `192.168.2.0`.

### Q131. Is `192.168.1.10` in `192.168.1.0/24`?

**Answer:** Yes.

### Q132. Is `192.168.2.10` in `192.168.1.0/24`?

**Answer:** No.

### Q133. Therefore, why does Host-A use the router to reach Host-C?

**Answer:** Host-C's IP belongs to a different subnet.

---

# 18. Trace the Practical

## Q134. Trace Host-A → Host-B.

**Answer:**

```text
Host-A
  |
  | Check ARP cache
  |
  | MISS
  v
Broadcast ARP Request
  |
  v
Host-B
  |
  | ARP Reply
  v
Host-A
  |
  | Cache Host-B MAC
  |
  | Build IP packet
  |
  | Encapsulate in Ethernet frame
  v
Host-B
```

The practical then repeats the communication to demonstrate an ARP cache HIT. fileciteturn0file0L675-L689

---

## Q135. Trace Host-A → Host-C.

**Answer:**

```text
Host-A
  |
  | Destination is remote
  |
  | ARP for gateway
  v
R1-LAN1
  |
  | Receive IP packet
  | TTL = TTL - 1
  |
  | Find outbound interface
  v
R1-LAN2
  |
  | ARP for Host-C
  v
Host-C
```

The router then sends a newly framed Ethernet packet on LAN-2 while keeping the IP source/destination unchanged. fileciteturn0file0L463-L519

---

# 19. Short One-Line Viva Questions

### Q136. Full form of ARP?

**Answer:** Address Resolution Protocol.

### Q137. Full form of RARP?

**Answer:** Reverse Address Resolution Protocol.

### Q138. Full form of LAN?

**Answer:** Local Area Network.

### Q139. Full form of IP?

**Answer:** Internet Protocol.

### Q140. Full form of MAC?

**Answer:** Media Access Control.

### Q141. Full form of TTL?

**Answer:** Time To Live.

### Q142. ARP mapping direction?

**Answer:** IP → MAC.

### Q143. RARP mapping direction?

**Answer:** MAC → IP.

### Q144. ARP Request destination?

**Answer:** Ethernet broadcast MAC `FF:FF:FF:FF:FF:FF`.

### Q145. ARP Reply destination?

**Answer:** Usually the requester's MAC address.

### Q146. IP address layer?

**Answer:** Layer 3.

### Q147. MAC address layer?

**Answer:** Layer 2.

### Q148. Routing layer?

**Answer:** Layer 3.

### Q149. Device used to connect different IP networks?

**Answer:** Router.

### Q150. Device commonly used to connect devices within a LAN?

**Answer:** Switch.

---

# 20. Very Likely Viva Questions

If the examiner asks only a few questions, these are especially important to understand:

### 1. What is ARP?

**IP-to-MAC address resolution on the local network.**

### 2. Explain ARP Request and Reply.

**Request is broadcast; the device owning the target IP sends a unicast Reply containing its MAC.**

### 3. What is RARP?

**A mechanism in which a device uses its MAC address to obtain an IP address from a server.**

### 4. ARP vs RARP?

**ARP: IP → MAC. RARP: MAC → IP.**

### 5. Why is ARP cache used?

**To avoid repeatedly broadcasting ARP Requests for known mappings.**

### 6. What happens after ARP cache expiry?

**The mapping is removed and ARP must be performed again.**

### 7. Why does Host-A use the router for Host-C?

**Host-C is on a different subnet.**

### 8. Which MAC does Host-A use for a remote destination?

**The MAC of the default gateway/router interface on the local LAN.**

### 9. What changes at a router?

**The Ethernet frame changes and TTL is decremented; the final source/destination IP addresses remain unchanged in this simulation.**

### 10. What happens when TTL reaches zero?

**The router drops the packet.**

### 11. Why is the ARP Request broadcast?

**Because the sender initially does not know which device owns the target IP.**

### 12. Why is the ARP Reply unicast?

**Because the responder knows the requester's MAC address.**

---

# 21. Final Mental Model

Remember the practical as three separate questions:

## A. "I know the IP, but I need the MAC."

Use **ARP**:

```text
IP → ARP → MAC
```

## B. "I know my MAC, but I don't have an IP."

Use **RARP** in this practical:

```text
MAC → RARP → IP
```

## C. "The destination is on another network."

Use the **router**:

```text
Host
  ↓
ARP for gateway
  ↓
Router
  ↓
Route to destination subnet
  ↓
ARP on outgoing LAN
  ↓
Destination Host
```

The core flow demonstrated by the program is therefore:

```text
              LOCAL DESTINATION
Host ── ARP ───────────────→ Host
 │
 │
 │ REMOTE DESTINATION
 │
 └── ARP → Gateway → Router → ARP → Destination

                     TTL decreases at router
```

---

# 22. Practical Configuration to Memorize


| Device      | IP             | MAC                 | Network |
| ----------- | -------------- | ------------------- | ------- |
| Host-A      | `192.168.1.10` | `00:00:00:00:00:01` | LAN-1   |
| Host-B      | `192.168.1.20` | `00:00:00:00:00:02` | LAN-1   |
| Host-C      | `192.168.2.10` | `00:00:00:00:00:03` | LAN-2   |
| R1-LAN1     | `192.168.1.1`  | `00:AA:00:00:00:01` | LAN-1   |
| R1-LAN2     | `192.168.2.1`  | `00:AA:00:00:00:02` | LAN-2   |
| RARP Server | —              | `AA:AA:AA:AA:AA:AA` | LAN-1   |


The practical's exact host, router, and RARP configuration is defined in `main()`. fileciteturn0file0L579-L650

---

## Key Takeaway

For the viva, understand the **packet path**, not just the definitions:

```text
SAME SUBNET:

Host-A
  ↓
ARP Request (broadcast)
  ↓
Host-B
  ↓
ARP Reply (unicast)
  ↓
Host-A
  ↓
Ethernet frame → Host-B


DIFFERENT SUBNET:

Host-A
  ↓
ARP Request → Gateway
  ↓
Gateway MAC learned
  ↓
Ethernet frame → Router
  ↓
Router decrements TTL
  ↓
Router selects outgoing interface
  ↓
ARP → Host-C
  ↓
New Ethernet frame
  ↓
Host-C
```

The practical specifically demonstrates successful/failed RARP, same-subnet delivery, ARP caching and expiry, ARP failure, cross-subnet routing, and TTL expiration. fileciteturn0file0L654-L735