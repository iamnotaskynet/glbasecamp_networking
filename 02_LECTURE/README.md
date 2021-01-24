

### Link aggregation and redundancy

- Logical aggregation of similar links between switches
- High banwidth
- Load shares accross links
- View as one logical port to STP
- Redundancy - outomatic failover

### Link redundancy

802.3

| 7 | 1 | 6 | 6 | 2 | 46-1500 | 4 |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| Preamble | SOF| Destination Address| Source Address | Length | 802.2 Header and Data | FCS |

<i>SOF = Start-of-frame delimiter</i>

<i>FCS = Frame Check Sequence</i>


Broadcast storm

Duplicate frames and table corruption

### STP

[STP](https://en.wikipedia.org/wiki/Spanning_Tree_Protocol)

[EtherChannel](https://en.wikipedia.org/wiki/EtherChannel)

STP executes algorithm called spanning-tree algorithm:
- Elects one root bridge per broadcast domain
- Selects one root port pet non-root bridge
- Selects one designated port per segment
- Block user traffic on nondesignated ports

### STP: Bridge ID and root selection

- Exchange of BPDU (default = sent every 2 seconds)
- Root bridge = brifge with the lowest bridge ID
- Bridge ID = Brifge priority, MAC Address

### STP: Timers

Spanning tree transits each port throught several different states:


```
________________________
|       Blockong        |
|(loss of BPDU detected)|
|  ( max age = 30 sec)  |
|_______________________|
            |                   ______________________
            |                   |     Blocking       |          _________________
____________V___________        |(moves to listening |          |               |
|      Listening        |       | after it decides it|<---------| Link comes up |
|(forward delay= 15 sec)|<------| is a root port or a|          |_______________|
|_______________________|       | designated port    |
            |                   |____________________|
            |
____________V___________
|      Listening        |
|(forward delay= 15 sec)|
|_______________________|
            |
            |
____________V___________
|                       |
|       Forwarding      |
|_______________________|
```
- Transition takes 30 to 50 seconds

### STP vs RSTP

STP:
- A topology change is generated on point T, then TCN is going up to the root.
- The root advertises the TC for max-age + forward delay.

RSTP:
- The originator of TC directly floods this information through the network.

### RSTP and Alternatives

[RSTP](https://en.wikipedia.org/wiki/Spanning_Tree_Protocol#Rapid_Spanning_Tree_Protocol)

RSTP has no timers.

[MC-LAG](https://en.wikipedia.org/wiki/Multi-chassis_link_aggregation_group)

[SPB](https://en.wikipedia.org/wiki/IEEE_802.1aq)

[TRILL](https://en.wikipedia.org/wiki/TRILL_(computing))

[ECMP](https://en.wikipedia.org/wiki/Equal-cost_multi-path_routing)