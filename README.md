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
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
