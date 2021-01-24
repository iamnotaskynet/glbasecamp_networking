

### OSI MODEL
| Layer | Device | Protocol |
| :---  |    :----:   |  :----: |
| 7. Application  | ALG/Firewall, IPS, IDS    | http(s), ftp, ssh |
| 6. Presentation | Transcoder                | ASCII/Unicode, jpeg/png |
| 5. Session      | Session Border Controller | ISO x.225, SQL, SIP/H323 VoIP SBC|
| 4. Transport    | Proxy, Firewall           | TCP/UDP |
| 3. Network      | Router, L3 Switch         | IP, OSPF, RIP, BGP |
| 2. Data Link    | NIC, Bridge, L2 Switch    | Frame Relay, HDLC, Ethernet (.1q) |
| 1. Physical     | NIC, Repeater, Hub        | Link encoding |

### OSI: PDU
| SENDER | (chunk) | RECIEVER |
| :----:  |    :----:   |  :----: |
| 7. Application  | DATA    | 7. Application |
| 6. Presentation | DATA    | 6. Presentation |
| 5. Session      | DATA    | 5. Session |
| 4. Transport    | SEGMENTS| 4. Transport |
| 3. Network      | PACKETS | 3. Network |
| 2. Data Link    | FRAMES  | 2. Data Link |
| 1. Physical     | BITS    | 1. Physical |

### OSI vs TCP/IP

<table>
    <thead>
        <tr>
            <th>OSI</th>
            <th>TCP/IP</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>7. Application</td>
            <td rowspan="3">4. Application</td>
        </tr>
        <tr>
            <td>6. Presentation</td>
        </tr>
        <tr>
            <td>5. Session</td>
        </tr>
        <tr>
            <td>4. Transport</td>
            <td>3. Transport</td>
        </tr>
        <tr>
            <td>3. Network</td>
            <td>2. Internet</td>
        </tr>
        <tr>
            <td>2. Data Link</td>
            <td rowspan="3">1. Network Access</td>
        </tr>
        <tr>
            <td>1. Physical</td>
        </tr>
    </tbody>
</table>

### TCP/IP: layers addressing

<table>
    <thead>
        <tr>
            <th>Physical</th>
            <th>Data Link</th>
            <th>Network</th>
            <th>Transport</th>
            <th>Upper protocols</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Timing and synchronization bits</td>
            <td>Destination and Source Physical addressing</td>
            <td>Destination and Source Logical Network addressing</td>
            <td>Destination and Source Process number (port)</td>
            <td>Encoded Application Data</td>
        </tr>
    </tbody>
</table>


### L1: CSMA/Cx and collisions
[CSMA](https://en.wikipedia.org/wiki/Carrier-sense_multiple_access)

[CSMA/CD](https://en.wikipedia.org/wiki/Carrier-sense_multiple_access_with_collision_detection)

[CSMA/CA](https://en.wikipedia.org/wiki/Carrier-sense_multiple_access_with_collision_avoidance)

[RTS/CTS](https://en.wikipedia.org/wiki/IEEE_802.11_RTS/CTS)

### L2: technologies and protocols

Ethernet frame format

Ethernet

| 8 | 6 | 6 | 2 | 46-1500 | 4 |
| :----: | :----: | :----: | :----: | :----: | :----: |
| Preamble | Destination Address| Source Address | Type | Data | FCS |

802.3

| 7 | 1 | 6 | 6 | 2 | 46-1500 | 4 |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| Preamble | SOF| Destination Address| Source Address | Length | 802.2 Header and Data | FCS |

<i>SOF = Start-of-frame delimiter</i>

<i>FCS = Frame Check Sequence</i>

### MAC Address

[Media Access Control](https://en.wikipedia.org/wiki/MAC_address)

<table style="text-align:center;">
    <!-- <thead>
        <tr>
            <th></th>
            <th></th>
            <th></th>
            <th></th>
        </tr>
    </thead> -->
    <tbody>
        <tr>
            <td>1</td>
            <td>1</td>
            <td>22 Bits</td>
            <td>24 Bits</td>
        </tr>
        <tr>
            <td>Broadcast</td>
            <td>Local</td>
            <td>OUI (Organizationally Unique Identifier)</td>
            <td>Vendor Assigned</td>
        </tr>
        <tr>
            <td colspan="4">48 Bits</td>
        </tr>
    </tbody>
</table>


### ARP Protocol

[Address Resolution Protocol](https://en.wikipedia.org/wiki/Address_Resolution_Protocol)

[gratuitous ARP](https://en.wikipedia.org/wiki/Address_Resolution_Protocol#ARP_announcements)

### Switch operation

[Network switch](https://en.wikipedia.org/wiki/Network_switch)

### VLAN

[VLAN](https://en.wikipedia.org/wiki/Virtual_LAN)

- VLAN is independed LAN network
- VLAN = Broadcast Domain = Logical Network (Subnet)
- VLNA address:
    - segmentation
    - security
    - network flexibility

### VLAN: 802.1q

<table style="text-align:center;">
    <thead>
        <tr>
            <th colspan="5">Original Frame</th>
    </thead>
    <tbody>
        <tr>
            <td>Dest</td>
            <td>Src</td>
            <td>Len/Etype</td>
            <td>Data</td>
            <td><del>FCS</del></td>
        </tr>
    </tbody>
</table>

<table style="text-align:center;">
    <thead>
        <tr>
            <th colspan="6">Tagged Frame</th>
    </thead>
    <tbody>
        <tr>
            <td>Dest</td>
            <td>Src</td>
            <td>Tag</td>
            <td>Len/Etype</td>
            <td>Data</td>
            <td style="background-color: lightgrey;">FCS</td>
        </tr>
    </tbody>
</table>

<table style="text-align:center;">
    <thead>
        <tr>
            <th colspan="6">Tagged Frame: Tag</th>
    </thead>
    <tbody>
        <tr>
            <td>Ether Type (0x8100)</td>
            <td>PRI</td>
            <td>TREF</td>
            <td>VLAN ID</td>
        </tr>
    </tbody>
</table>

<i>TREF = Token Ring Encapsulation Flag</i>

### VLAN and trunk: tagged and untagged traffic

[Link aggregation](https://en.wikipedia.org/wiki/Link_aggregation)

[Trunking](https://en.wikipedia.org/wiki/Trunking)