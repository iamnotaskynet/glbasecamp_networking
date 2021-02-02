### 

[Proxy ARP](https://en.wikipedia.org/wiki/Proxy_ARP) 
-can emulate for VLAN virtual MAC address

### IPv4 addressing

#### 0.0.0.0 - 255.255.255.255

<table>
    <tbody>
        <tr>
            <td rowspan="2">An IP addr is a 32-bit binary number</td>
            <td colspan="4">Example</td>
        </tr>
        <tr>
            <td colspan="4">10101100 00010000 10000000 00010001</td>
        </tr>
        <tr>
            <td>For readability, the 32 binary nubmber <br> can be divided into four 8-bit octets</td>
            <td>10101100</td>
            <td>00010000</td>
            <td>10000000</td>
            <td>00010001</td>
        </tr>
        <tr>
            <td>Each octet (or byte) can be converted to decimal</td>
            <td>172</td>
            <td>16</td>
            <td>128</td>
            <td>17</td>
        </tr>
        <tr>
            <td>The addr can be writen in dotted decimal notation</td>
            <td colspan="4">172.16.128.17</td>
        </tr>
    </tbody>
</table>

### IPv4 address: network and host part

- The uniquely identify each device on an IP network.
- Every host (computerm networking device, peripheral) must have a uniqye address.
- An IP address consists of two parts:
    - Network ID:
        - Identifies the network of wich the host is a part
        - Used by routers to maintain information about routes
    - Host ID"
        - Identifies the individual host
        - Assigned by  organizations to individual devices

### IPv4 address: network mask

<span style="color: white; font-weight: bold; background: blue; border: 2px black solid;">Network.Host</span>

<table >
    <thead>
        <tr style="color: white; background: grey; border: 4px white solid;">
            <th >10.</th>
            <th>10.</th>
            <th>10.</th>
            <th>10.</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style=" background: lightgreen; border: 4px white solid;">255.</td>
            <td style=" background: lightgreen; border: 4px white solid;">255.</td>
            <td style=" background: lightpink; border: 4px white solid;">0.</td>
            <td style=" background: lightpink; border: 4px white solid;">0.</td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style=" background: lightgreen; border: 4px white solid;">00001010</td>
            <td style=" background: lightgreen; border: 4px white solid;">00001010</td>
            <td style=" background: lightpink; border: 4px white solid;">00001010</td>
            <td style=" background: lightpink; border: 4px white solid;">00001010</td>
        </tr>
        <tr>
            <td style=" background: lightgreen; border: 4px white solid;">11111111</td>
            <td style=" background: lightgreen; border: 4px white solid;">11111111</td>
            <td style=" background: lightpink; border: 4px white solid;">00000000</td>
            <td style=" background: lightpink; border: 4px white solid;">00000000</td>
        </tr>
    </tbody>
</table>


### IPv4 address: network and broadcast

- Network Addresses &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10.10.0.0

<table>
    <tr>
        <th style="color: white; font-weight: bold; background: blue; border: 2px black solid;">Network</th>
        <th style="color: black; font-weight: bold; background: orange; border: 2px black solid;">00000000.00000000</th>
    </tr>
</table>

- Broadcast Addresses &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10.10.255.255

<table>
    <tr>
        <th style="color: white; font-weight: bold; background: blue; border: 2px black solid;">Network</th>
        <th style="color: black; font-weight: bold; background: orange; border: 2px black solid;">11111111.11111111</th>
    </tr>
</table>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10.10.10.10/16 (/16 = 255.255.0.0)

### IPv4 classes and masks

<h4><span style="color: blue; font-weight: bold;">A B C ... Easy as 1 2 3 </span></h4>

Class A ... First 1 bit fixed 
<span style="font-weight: bold; background: lightblue; padding: 4px;">0 x x x x x x x</span>.
<span style="font-weight: bold; border: 2px black solid; background: orange; padding: 4px;">Host</span>.
<span style="font-weight: bold; border: 2px black solid; background: orange; padding: 4px;">Host</span>.
<span style="font-weight: bold; border: 2px black solid; background: orange; padding: 4px;">Host</span>

Class B ... First 2 bit fixed 
<span style="font-weight: bold; background: lightblue; padding: 4px;">1 0 x x x x x x</span>.
<span style="font-weight: bold; border: 2px black solid; background: blue; color: white; padding: 4px;">Network</span>.
<span style="font-weight: bold; border: 2px black solid; background: orange; padding: 4px;">Host</span>.
<span style="font-weight: bold; border: 2px black solid; background: orange; padding: 4px;">Host</span>

Class C ... First 3 bit fixed 
<span style="font-weight: bold; background: lightblue; padding: 4px;">1 1 0 x x x x x</span>.
<span style="font-weight: bold; border: 2px black solid; background: blue; color: white; padding: 4px;">Network</span>.
<span style="font-weight: bold; border: 2px black solid; background: blue; color: white; padding: 4px;">Network</span>.
<span style="font-weight: bold; border: 2px black solid; background: orange; padding: 4px;">Host</span>


<table>
    <thead>
        <tr style="color: white; background: blue;">
            <th> IP Address Class</th>
            <th> First Octet Binary Value</th>
            <th> First Octet Decimal Value</th>
            <th> Possible Number of Hosts</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Class A</td>
            <td>1-126</td>
            <td><ins>0</ins>0000001 to <ins>0</ins>1111110*</td>
            <td>16,777,214</td>
        </tr>
        <tr>
            <td>Class B</td>
            <td>128-191</td>
            <td><ins>10</ins>000000 to <ins>10</ins>111111</td>
            <td>65,534</td>
        </tr>
        <tr>
            <td>Class C</td>
            <td>192-223</td>
            <td><ins>110</ins>00000 to <ins>110</ins>11111</td>
            <td>254</td>
        </tr>
    </tbody>
</table>

<span style="border: 4px black solid;"> *127 (01111111) is a Class A address reserved for loopback testing and cnnotbe assigned to a network.</span>

### Class C subnetting

<p  style="display:inline-table;">
<span style="background: blue; color: white; padding: 4px;">Network</span>.
<span style="background: blue; color: white; padding: 4px;">Network</span>.
<span style="background: blue; color: white; padding: 4px;">Network</span>.
<table style="display: inline; display:inline-table">
    <tr style="background: yellow; border: 2px black solid;">
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
    </tr>
<table>
</p>


<table style="border: 2px black solid; border-collapse: collapse; text-align: center;">
    <thead>
        <tr style="background: blue; color: white; ">
            <th style="border: 2px black solid;">Number of Bits Borrowed <br> (S)</th>
            <th style="border: 2px black solid;">Number of Subnets Possible <br> (2<sup>S</sup>)</th>
            <th style="border: 2px black solid;">Number of Bits Remaining in Host ID <br>(8 - S = h)</th>
            <th style="border: 2px black solid;">Number of Hosts Possible per Subnet <br> (2<sup>h</sup> - 2)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="border: 2px black solid;">1</td>
            <td style="border: 2px black solid;">2</td>
            <td style="border: 2px black solid;">7</td>
            <td style="border: 2px black solid;">126</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">2</td>
            <td style="border: 2px black solid;">4</td>
            <td style="border: 2px black solid;">6</td>
            <td style="border: 2px black solid;">62</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">3</td>
            <td style="border: 2px black solid;">8</td>
            <td style="border: 2px black solid;">5</td>
            <td style="border: 2px black solid;">30</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">4</td>
            <td style="border: 2px black solid;">16</td>
            <td style="border: 2px black solid;">4</td>
            <td style="border: 2px black solid;">14</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">5</td>
            <td style="border: 2px black solid;">32</td>
            <td style="border: 2px black solid;">3</td>
            <td style="border: 2px black solid;">6</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">6</td>
            <td style="border: 2px black solid;">64</td>
            <td style="border: 2px black solid;">2</td>
            <td style="border: 2px black solid;">2</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">7</td>
            <td style="border: 2px black solid;">128</td>
            <td style="border: 2px black solid;">1</td>
            <td style="border: 2px black solid;">0</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">8</td>
            <td style="border: 2px black solid;">256</td>
            <td style="border: 2px black solid;">0</td>
            <td style="border: 2px black solid;">0</td>
        </tr>
    </tbody>
</table>

### Class B subnetting

<p  style="display:inline;">
<span style="background: blue; color: white; padding: 4px;">Network</span>.
<span style="background: blue; color: white; padding: 4px;">Network</span>.
<table style="display: inline; display:inline">
    <tr style="background: yellow; border: 2px black solid; display: inline-table;">
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
    </tr>
</table>.
<table style="display: inline; display:inline">
    <tr style="background: yellow; border: 2px black solid; display: inline-table;">
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
        <td style="background: orange; border: 2px black solid; padding: 2px;">&#32;.</td>
    </tr>
</table>
</p>


<table style="border: 2px black solid; border-collapse: collapse; text-align: center;">
    <thead>
        <tr style="background: blue; color: white; ">
            <th style="border: 2px black solid;">Number of Bits Borrowed <br> (S)</th>
            <th style="border: 2px black solid;">Number of Subnets Possible <br> (2<sup>S</sup>)</th>
            <th style="border: 2px black solid;">Number of Bits Remaining in Host ID <br>(8 - S = h)</th>
            <th style="border: 2px black solid;">Number of Hosts Possible per Subnet <br> (2<sup>h</sup> - 2)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="border: 2px black solid;">1</td>
            <td style="border: 2px black solid;">2</td>
            <td style="border: 2px black solid;">15</td>
            <td style="border: 2px black solid;">32,766</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">2</td>
            <td style="border: 2px black solid;">4</td>
            <td style="border: 2px black solid;">14</td>
            <td style="border: 2px black solid;">16,382</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">3</td>
            <td style="border: 2px black solid;">8</td>
            <td style="border: 2px black solid;">13</td>
            <td style="border: 2px black solid;">8,190</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">...</td>
            <td style="border: 2px black solid;">...</td>
            <td style="border: 2px black solid;">...</td>
            <td style="border: 2px black solid;">...</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">13</td>
            <td style="border: 2px black solid;">8192</td>
            <td style="border: 2px black solid;">3</td>
            <td style="border: 2px black solid;">6</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">14</td>
            <td style="border: 2px black solid;">16384</td>
            <td style="border: 2px black solid;">2</td>
            <td style="border: 2px black solid;">2</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">15</td>
            <td style="border: 2px black solid;">32768</td>
            <td style="border: 2px black solid;">1</td>
            <td style="border: 2px black solid;">0</td>
        </tr>
        <tr>
            <td style="border: 2px black solid;">16</td>
            <td style="border: 2px black solid;">65636</td>
            <td style="border: 2px black solid;">0</td>
            <td style="border: 2px black solid;">0</td>
        </tr>
    </tbody>
</table>

### Subnet mask

- Subnet masks, like IP addresses, are represented in the dotted decimal format, such as 255.255.255.0
- The number 1 reflects the network part of the IP address.

<table style="border-spacing: 4px;">
    <thead>
        <tr style="border-bottom: 4px solid blue;">
            <th>128</th>
            <th>64</th>
            <th>32</th>
            <th>16</th>
            <th>8</th>
            <th>4</th>
            <th>2</th>
            <th>1</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody >
        <tr>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>=</td>
            <td>128</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>=</td>
            <td>192</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>=</td>
            <td>224</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>=</td>
            <td>240</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>0</td>
            <td>0</td>
            <td>=</td>
            <td>248</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>0</td>
            <td>=</td>
            <td>252</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>0</td>
            <td>=</td>
            <td>254</td>
        </tr>
        <tr>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td style="background: lightblue;">1</td>
            <td>=</td>
            <td>255</td>
        </tr>
    </tbody>
</table>

### IPv4 public and reserved space

<table >
    <thead>
        <tr style="background: blue; color: white;">
            <th style="border: 2px black solid">Class</th>
            <th style="border: 2px black solid">Public IP Ranges</th>
        </tr>
    </thead>
    <tbody >
        <tr>
            <td style="border: 2px black solid">A</td>
            <td style="border: 2px black solid">1.0.0.0 to 9.255.255.255 <br>11.0.0.0 to 126.255.255.255 </td>
        </tr>
        <tr>
            <td style="border: 2px black solid">B</td>
            <td style="border: 2px black solid">128.0.0.0 to 172.15.255.255 <br>172.32.0.0 to 191.255.255.255 </td>
        </tr>
        <tr>
            <td style="border: 2px black solid">C</td>
            <td style="border: 2px black solid">192.0.0.0 to 192.167.255.255 <br>192.169.0.0 to 223.255.255.255</td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr style="background: blue; color: white;">
            <th style="border: 2px black solid">Class</th>
            <th style="border: 2px black solid">Private Address Ranges</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="border: 2px black solid">A</td>
            <td style="border: 2px black solid">10.0.0.0 to 10.255.255.255</td>
        </tr>
        <tr>
            <td style="border: 2px black solid">B</td>
            <td style="border: 2px black solid">172.16.0.0 to 172.31.255.255</td>
        </tr>
        <tr>
            <td style="border: 2px black solid">C</td>
            <td style="border: 2px black solid">192.168.0.0 to 192.168.255.255</td>
        </tr>
    </tbody>
</table>

- 127.0.0.0/8, (ping 127.0.0.1)
- 169.254.x.x/16, 198.18.0.0/15
- 224.0.0.0/24, 224.0.1.0/24 plus some others
- RFC 3330 and newer

### Unicast, Broadcast, Multicast

Unicast = One -> One

Broadcast = One -> Everyone

Multicast = One -> Group

### IPv4 datagram and technologies

#### IPv4 datagram

<table style="text-align: center;">
<thead>
    <tr>
        <th colspan="2">---- Byte 1 ----</th>
        <th colspan="2">---- Byte 2 ----</th>
        <th colspan="2">---- Byte 3 ----</th>
        <th colspan="2">---- Byte 4 ----</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td ></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td style="background: orange; border: 2px black solid;">Ver.</td>
        <td style="background: orange; border: 2px black solid;">IHL</td>
        <td colspan="2" style="background: yellow; border: 2px black solid;">Service Type</td>
        <td colspan="4" style="background: lightgreen; border: 2px black solid;">Packet Length</td>
    </tr>
    <tr>
        <td colspan="4" style="background: lightblue; border: 2px black solid;">Identification</td>
        <td colspan="1" style="background: lightblue; border: 2px black solid;">Flag</td>
        <td colspan="3" style="background: lightgreen; border: 2px black solid;">Fragment Offset</td>
    </tr>
    <tr>
        <td colspan="2" style="background: yellow; border: 2px black solid;">Time to Live</td>
        <td colspan="2" style="background: yellow; border: 2px black solid;">Protocol</td>
        <td colspan="4" style="background: lightgreen; border: 2px black solid;">Header Checksum</td>
    </tr>
    <tr>
        <td colspan="8" style="background: lightblue; border: 2px black solid;">Source Addrtess</td>
    </tr>
    <tr>
        <td colspan="8" style="background: lightblue; border: 2px black solid;">Destination Address</td>
    </tr>
    <tr>
        <td colspan="7" style="background: lightblue; border: 2px black solid;">Options</td>
        <td style="background: yellow; border: 2px black solid;">Padding</td>
    </tr>
</tbody>
</table>

### IPv4 fragmentation

```
<------------- IPv4 Datagrams ------------->
____________________________________________
| IPv4 | UDP  |                             |   First Fragment
|Header|Header|            UDP Data         |   Total Length = 1500
|______|______|_____________________________|   UDP Length = 3000
Offset=0
MF=1    <----- IP Payload (1480 bytes) ----->
____________________________________________
| IPv4 |                                    |   Second Fragment
|Header|            UDP Data                |   Total Length = 1500
|______|____________________________________|
Offset=185
MF=1
____________________
| IPv4 |            |                           Last Fragment
|Header|  UDP Data  |                           Total Length = 60
|______|____________|
        <----------->
        IP Payload (40 bytes)
Offset=370                          Original IPv4 Datagram Total Length:
MF=0                                    20 + 8 +2992 = 3020 bytes
```

### [PMTUD](https://en.wikipedia.org/wiki/Path_MTU_Discovery)

(img)

<table style="text-align: center;">
    <tr>
        <td colspan="8">128 bits</td>
    </tr>
    <tr>
        <td colspan="4">Network Prefix</td>
        <td colspan="4">Interface ID</td>
    </tr>
    <tr>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
        <td style="border: 2px black solid;">XXXX</td>
    </tr>
</table>

XXXX = 0000 through FFFF

3.4 x 10<sup>38</sup> = 1e+38 × 3.4 

### IPv6 Addreses

<table style="table-layout:fixed; min-width: 700px; text-align: center;">
    <colgroup >
        <col span="1"  style="width:5%;">
        <col span="1"  style="width:35%;">
        <col span="1"  style="width:15%;">
        <col span="1"  style="width:45%;">
    </colgroup>
    <tr>
        <td colspan="2">Provider</td>
        <!-- <td></td> -->
        <td>Site</td>
        <td>Host</td>
    </tr>
    <tr>
        <td>3 bits</td>
        <td>45 bits</td>
        <td>16 bits</td>
        <td>64 bits</td>
    </tr>
    <tr>
        <td style="border: 2px black solid;">001</td>
        <td style="border: 2px black solid;">Global Routing Prefix</td>
        <td style="border: 2px black solid;">Subnet ID</td>
        <td style="border: 2px black solid;">Interface ID</td>
    </tr>
</table>

### IPv6 addreses compression

Example 1:
- 2031:0000:130F:0000:0000:09C0:876A:130B = 
- 2031:0:130F:0:0:09C0:876A:130B (compressed form) = 
- 2031:0:130F::09C0:876A:130B (compressed form) 

Example 1:
= FF01:0:0:0:0:1 = FF01::1

### IPv6 addres: Link and Site Local

<table style="table-layout:fixed; min-width: 900px; text-align: center;">
<colgroup >
        <col span="1"  style="width:15%;">
        <col span="1"  style="width:35%;">
        <col span="1"  style="width:50%;">
    </colgroup>
     <tr>
        <td colspan="3">128 bits</td>
    </tr>
    <tr>
        <td style="border: 2px black solid;">1111 1110 10<br>FE80::/10</td>
        <td style="border: 2px black solid;">0</td>
        <td style="border: 2px black solid;">Interface ID</td>
    </tr>
    <tr>
        <td>10 bits</td>
        <td></td>
        <td>64 bits</td>
    </tr>
</table>

<table style="table-layout:fixed; min-width: 900px; text-align: center;">
    <colgroup >
        <col span="1"  style="width:10%;">
        <col span="1"  style="width:30%;">
        <col span="1"  style="width:10%;">
        <col span="1"  style="width:50%;">
    </colgroup>
     <tr>
        <td colspan="4">128 bits</td>
    </tr>
    <tr>
        <td style="border: 2px black solid;">1111 1110 10<br>FEC0::/10</td>
        <td style="border: 2px black solid;">0</td>
        <td style="border: 2px black solid;">Subnet ID</td>
        <td style="border: 2px black solid;">Interface ID</td>
    </tr>
     <tr>
        <td>10 bits</td>
        <td></td>
        <td>16 bits</td>
        <td>64 bits</td>
    </tr>
</table>

### IPv6 addres: exampels

<table>
<thead>
    <tr style="backgorund: gray; color white; text-align: center;">
        <th>Address</th>
        <th>Use case</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>::/128</td>
        <td>Unspecified</td>
    </tr>
    <tr>
        <td>::1/128</td>
        <td>Loopback</td>
    </tr>
    <tr>
        <td>::/0</td>
        <td>Default route</td>
    </tr>
    <tr>
        <td>2001:db8::/32</td>
        <td>Examples</td>
    </tr>
    <tr>
        <td>fe80::/10</td>
        <td>Link-local unicast addresses</td>
    </tr>
    <tr>
        <td>2d03:2880:f102:f102:83:face:b00c:0:25de</td>
        <td>Public unicast address<br>(www.facebook.com)</td>
    </tr>
    <tr>
        <td>2404:6800:4005:80d::2004</td>
        <td>Public unicast address<br>(www.google.com)</td>
    </tr>
</tbody>
</table>

### IPv6 datagram and technologies

 - <span style="border: 2px black solid; background: lightgray;">____</span> Field name kept from IPv4 to IPv6
 - <span style="border: 2px black solid; background: white;">____</span> Field nto kept in IPv6
 - <span style="border: 2px black solid; background: darkgray;">____</span> Name and position changed in IPv6
 - <span style="border: 2px black solid; background: gray;">____</span> New field in IPv6



<table style="text-align: center;">
    <caption>IPv4 Header</caption>
    <colgroup >
        <col span="1"  style="width:20%;">
        <col span="1"  style="width:10%;">
        <col span="1"  style="width:30%;">
        <col span="1"  style="width:15%;">
        <col span="1"  style="width:35%;">
    </colgroup>
    <tr>
        <td style="border: 2px black solid; background: lightgray;" >Version</td>
        <td style="border: 2px black solid; background: white;" >IHL</td>
        <td style="border: 2px black solid; background: darkgray;" >Type of Service</td>
        <td  style="border: 2px black solid; background: darkgray;" colspan="2">Total Length</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: white;" colspan="3">Identification</td>
        <td style="border: 2px black solid; background: white;">Flags</td>
        <td style="border: 2px black solid; background: white;">Fragment Offset</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: darkgray;" colspan="2">Time to Live</td>
        <td style="border: 2px black solid; background: darkgray;">Protocol</td>
        <td style="border: 2px black solid; background: white;" colspan="2">Header Checksum</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: lightgray;" colspan="5">Source Address</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: lightgray;" colspan="5">Destination Address</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: white;" colspan="4">Options</td>
        <td style="border: 2px black solid; background: white;">Padding</td>
    </tr>
</table>

<table style="text-align: center;">
    <caption>IPv6 Header</caption>
    <colgroup >
        <col span="1"  style="width:20%;">
        <col span="1"  style="width:30%;">
        <col span="1"  style="width:25%;">
        <col span="1"  style="width:25%;">
    </colgroup>
    <tr>
        <td style="border: 2px black solid; background: lightgray;" >Version</td>
        <td style="border: 2px black solid; background: darkgray;" >Traffic Class</td>
        <td style="border: 2px black solid; background: lightgray;"  colspan="2">Flow Label</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: darkgray;"  colspan="2">Payload Length</td>
        <td style="border: 2px black solid; background: darkgray;" >Next Header</td>
        <td style="border: 2px black solid; background: darkgray;" >Hop Limit</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: lightgray;"  colspan="5">Source Address</td>
    </tr>
    <tr>
        <td style="border: 2px black solid; background: lightgray;"  colspan="5">Destination Address</td>
    </tr>
</table>


### IPv6 Header (1:33:01)