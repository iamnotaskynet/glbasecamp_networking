

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

### Cisco IOS

\> - user
\# - admin

| commands | description |
| :--- | :--- |
| ```exit``` | exits from prompt, mode, config, etc |
| ```enable``` | goes from user to admin | 
| ```configure``` | goes to configuring mode |
| Ctrl + A | goes to start of prompt |
| Ctrl + E | goes to end of prompt |
| Ctrl + W | deletes last word |
| ```copy running-config startuo-config``` | sets current state of config to be loaded on next startup |
| ```write memory``` | (same as above) |
| ```wr``` | (same as above) |
| ```show flash``` |  |
| ```dir unix:``` |  |
| ```copy running-config unix:1.txt``` |  |
| ```show running-config``` |  |
| ```erase start``` | !!! |
| ```show ip inter bri``` |  |


```config.txt
no shutdown
```
### Global settings

| commands | description |
| :--- | :--- |
| ```hostname SW-A2``` | Set device hostname |
| ```clock timezone EET 2 0``` | Set timezone |
| ```clock summer-time EET recuring last Sat Mar 3:00 last Sat Oct 3:00``` | Set summer/winter time change |
| ```ip domain-name set example.com``` | Domain name required for ssh |
| ```ip name-server 1.2.3.4``` | DNS server |
| ```service timestamps log datetime localtime``` | Syslog timestamps. Usefull for security |
| ```service password encryption``` | Encrypt passwords |
| ```spanning-tree mode rapid-pvst``` | STP mode. Default enabled |
| ```spanning-tree extend system-id``` | STP PVST additional settings |

### Config :: Global settings

| commands | description |
| :--- | :--- |
| ```enable secret cisco```<br/>```(enable password cisco)``` | Set privileged mode password."secret" - is encrypted, "password" is plain text|
| ```username cisco privilege 15 secret cisco``` | Create local user, say for SSH. Privilege 15 means "enable"-level user |
| ```line vty 0 4```<br/>- transport input ssh telnet<br/>- login local<br/>- password cisco | telnet/ssh connections settings |
| ```crypto key generate rsa general-keys modulus 2048``` | Generate key for ssh. Requirement: domain-name should be set |

### Config :: Global settings :: VLANs

| commands | description |
| :--- | :--- |
| ```SW-A2(config)#vlan 100```| Create VLAN with ID 100 |
| ```SW-A2(config-vlan)#name Users```| Give it meaningful name |
| ```SW-A2(config-vlan)#^Z```| Ctrl+Z - exit configuration mode (or type exit) |
| ```SW-A2#wr``` | wr = write memory = copy run start|

### Config :: Interfaces :: L2

| commands | description |
| :--- | :--- |
| Interface type X/Y/Z | |
| Interface GigabitEthernet 0/0/0 | |
| In EVE-NG:interface Ethernet 0/0 | |
| Interface range E0/0 - 1 <br/>- switchport trunk encapsulation dot1q<br/>- switchport mode trunk | Configure range of ports as trunk <br/>-Ttrunk encapsulation<br/>- Trunk mode |
| Interface range E0/2 - 3 <br/>- switchport mode access<br/> - switchport access vlan 100 | Configure access interface <br/>- Access mode<br/>- Join interface into VLAN 100 |

### Config :: Interfaces :: L3

##### Switch:
- Interface E0/0
    - no switchport
    - ip address 1.2.3.4 255.255.255.0
    - no shutdown
- Interface vlan 100
    - ip address 1.2.3.4 255.255.255.0
    - no shutdown

##### Router:
- Interface
    - ip address 1.2.3.4 255.255.255.0
    - no shutdown

### Config :: STP

| commands | description |
| :--- | :--- |
| ```spanning-tree vlan 1-4094 root primary```| Set boot bridge |
| ```Interface E0/0```  <br/>- switchport trunk encapsulation dot1q<br/>- switchport mode trunk <br>- <b>spanning-tree portfast</b> network\|trunk | Trunk with STP mode as inter-switch link |
| ```Interface E0/0```  <br/>- switchport mode access <br/>- <b>spanning-tree portfast</b> edge | Access port with STP edge mode |
| ```show spanning-tree``` | Show STP topology |
| ```show spanning-tree``` | Display STP blocked ports |

### Config :: aggregated interface

| commands | description |
| :--- | :--- |
| ```Interface range e 0/0 - 1```| |
| ```Channel-group 1 mode on \| active``` | Tie physical ports into one logical interface port-channel 1 <br> Should be: same interface type, mode, speed, duplex, etc. |
| ```Show etherchannel summary``` | Check logical interfaces and grouping |
| ```Show run int port-channe 1``` | Show logical interface settings |

### Troubleshooting

### Check and roubleshoot

| commands | description |
| :--- | :--- |
| ```Show running```<br>```Show start``` | Display running/current config <br> Display saved config. |
| ```Show run interface e 0/0``` |  |
| ```Show ip interface brief \| excl una``` |  |
| ```Show run \| sec interface``` |  |
| ```Show interface trunk``` |  |
| ```Show vlan brief``` |  |
| ```Show cdp neighbors``` |  |
| ```Show ip arp/show arp``` |  |