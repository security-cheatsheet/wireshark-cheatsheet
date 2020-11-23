<p align="center">
  <img src="https://www.wireshark.org/assets/theme-2015/images/wireshark_logo.png">
  <br>
  <b> Wireshark Cheat Sheet</b>
</p>

<p> Wireshark, whose old name is Ethereal; It is a program that can run in many operating systems such as Windows, Linux, MacOS or Solaris and can analyze all the traffic going to network cards connected to computer. Analyze over 750 protocols Can capture packets and save them to a file. </p>

 Logical operators are available for all filtering.

+ <b> Example: </b> ```http & ip.src == 192.168.0.1```

+ <b> Management Frame: </b> The frame for the connection between the network device and the client.

+ <b> Control Frame: </b> Controls the integrity of data traffic between the network device and the client.

+ <b> Data Frame: </b> The frame on which the original data is transferred.

Only to show the outgoing packets from the management frame.
 
```
wlan.fc.type==0
```

To show incoming, outgoing packets through control frame.

```
wlan.fc.type==1
```

To show packets transferred over the data frame.

```
wlan.fc.type==2
```

Association lists the requests.

```
wlan.fc.type_subtype==0
```

Association lists the answers.

```
wlan.fc.type_subtype==1
```

Probe lists requests.

```
wlan.fc.type_subtype==4
```

Lists the probe responses.

```
wlan.fc.type_subtype==5
```

Lists Beacon signals / waves.

```
wlan.fc.type_subtype==8
```

Lists the Authentication requests.

```
wlan.fc.type_subtype==11
```

Lists deauthentication requests.

```
wlan.fc.type_subtype==12
```

TCP lists the outgoing packets to the xx port.

```
tcp.port == xx
```

TCP lists packages with the Source xx port.

```
tcp.srcport == xx
```

TCP lists packages with a destination xx port.

```
tcp.dstport == xx
```

UDP lists the outgoing packets to the xx port.

```
udp.port == xx
```

UDP lists packets with a destination xx port.

```
udp.srcport == xx
```

UDP lists packages that have the Source xx port.

```
udp.dstport == xx
```

Lists the HTTP Get requests.

```
http.request
```

Lists packages for the source or destination mac address.

```
wlan.addr == MAC-Address
```

The source lists packages that have a mac address.

```
wlan.sa == MAC-Address
```

Lists packages that have a target mac address.

```
wlan.da == MAC-Address
```

Filter traffic by IP, be it SOURCE or DESTINATION

```
ip.addr == IP-ADDR
```

Filter traffic by SOURCE IP Address

```
ip.src == IP-ADDR
```

Filter traffic by DESTINATION IP Address

```
ip.dst == IP-ADDR
```

Filter traffic by IP subnet

```
ip.addr == 127.0.0.1/24
```

Filter traffic by protocol name

```
arp
icmp
ftp
ssh
telnet
dns
http
```

Exclude IP address: remove traffic from and to IP address

```
!ip.addr ==192.168.0.1
```

Display traffic between two specific subnet

```
ip.addr == 192.168.0.1/24 and ip.addr == 192.168.1.1/24
```

Display traffic between two specific workstations

```
ip.addr == 192.168.0.1 and ip.addr == 192.168.0.2
```

Filter by MAC

```
eth.addr = 00:50:7f:c5:b6:78
```

Filter TCP port

```
tcp.port == 80
```

Filter TCP port source

```
tcp.srcport == 80
```

Filter TCP port destination

```
tcp.dstport == 80
```

Find user agents

```
http.user_agent contains Firefox
!http.user_agent contains || !http.user_agent contains Chrome
```

Filter broadcast traffic

```
!(arp or icmp or dns)
```

Filter IP address and port

```
tcp.port == 80 && ip.addr == 192.168.0.1
```

Filter all http get requests

```
http.request
```

Filter all http get requests and responses

```
http.request or http.response
```

Filter three way handshake

```
tcp.flags.syn==1 or (tcp.seq==1 and tcp.ack==1 and tcp.len==0 and tcp.analysis.initial_rtt)
```

Find files by type

```
frame contains “(attachment|tar|exe|zip|pdf)”
```

Find traffic based on keyword

```
tcp contains KEYWORD
frame contains KEYWORD
```

Detecting SYN Floods

```
tcp.flags.syn == 1 and tcp.flags.ack == 0
```

<b> Cloning an Existing Repository ( Clone with HTTPS ) </b>
```
root@ismailtasdelen:~# git clone https://github.com/ismailtasdelen/wireshark-cheatsheet.git
```

<b> Cloning an Existing Repository ( Clone with SSH ) </b>
```
root@ismailtasdelen:~# git clone git@github.com:ismailtasdelen/wireshark-cheatsheet.git
```

You can open the issues to this repo to be support and add new rss lists to this list.
