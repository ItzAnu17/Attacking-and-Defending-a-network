<h1>Attacking and monitoring a network</h1>


<h2>Description of the Project</h2>
The goal of the project is to create a small network, analyse ICMP and TCP packets which are incoming and ongoing within the network. Later, attack a user’s device and analyse the packets and see any changes from before. And finally, to implement a firewall to prevent TCP and ICMP flooding attack.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 
- <b>Wireshark</b>

<h2>Environments Used </h2>

- <b>Kali Linux</b> 

<h2>Project Details</h2>

<p align="center">
A small network was created with 4 users and a switch: <br/>
<img src="https://imgur.com/uxAe1AO.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Checking if we can ping each other. :  <br/>
<img src="https://imgur.com/oSEbR7Z.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
After connecting, we can use iperf on both the host and the client to monitor the
connectivity, recording TCP connection statistics such as Interval, Transfer and
Bandwidth. The command (iperf -s) was used to host a server. The following image
shows 192.168.65.178 (Anaaf) receiving TCP packets which are sent by
192.168.65.61 (Kunhuan): <br/>
<img src="https://imgur.com/H9BQ7ZM.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
ICMP flooding attack.<br/>
Two devices were used to attack a single PC. By using the command “$sudo hping3 -1 -flood 192.168.65.178”: 
<br/>
<img src="https://imgur.com/g26wWUY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On the host 192.168.65.178, the flow chart in Wireshark shows significant flooded packets
(brown line) coming, compared to those generated by ping (green line).:  
<br/>
<img src="https://imgur.com/xEyViPB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In Wireshark:  <br/>
The average Packets Per Second (PPS) is 45320.9/s and 70% of the packets were
dropped. It is clear that compared to level 2, there was a huge amount of packets
running.
<br />
<br />
<img src="https://imgur.com/jlPUQsZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://imgur.com/Tt1VDNQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
TCP Flooding Attack:  <br/>
TCP Flooding attack was done in a similar way, the command was “$sudo hping3
192.168.65.178 -S -p 22 --flood”
<img src="https://imgur.com/WeTxCFf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<br />
Firewall for ICMP flooding attack:  <br/>
<br/>
<br/>
Using firewalls are helpful in defending possible network attacks. To block ICMP attacks
we implemented the rules in iptable command. The rules are:
<br/>
<br/>
<img src="https://imgur.com/zoicLIM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
These rules will block every incoming ICMP packet from the specified IP addresses and
limit the ICMP packet rate. After we performed an ICMP flooding attack again, “No
response” packets were sniffed, which is different from level 3’s results, so we assume
the firewalls are functioning.  <br/>

<img src="https://imgur.com/8SxmBXb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!-- 
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
