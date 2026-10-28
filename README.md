## Ex. No: 5  VLAN Configuration Using a Managed Switch
Date:28.10.2026
Name:LOHINI S
________________________________________
# Objective
To configure Virtual Local Area Networks (VLANs) on a managed switch and verify that hosts within the same VLAN can communicate while others cannot.
________________________________________
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Managed Switch (e.g., 2960)<br>
•	4 PCs<br>
•	Straight-through Ethernet cables<br>
________________________________________
# Network Topology Diagram
Description:<br>
•	PC0 and PC1 are assigned to VLAN 10.<br>
•	PC2 and PC3 are assigned to VLAN 20.<br>
•	All PCs are connected to different ports on the same switch.<br>
(Insert screenshot of your Packet Tracer setup here)<br>

<img width="1098" height="745" alt="image" src="https://github.com/user-attachments/assets/c66570ac-aa0c-489b-baea-4d6d43b71237" />

________________________________________
# IP Addressing Table
Device	VLAN	IP Address	Subnet Mask	Port<br>
PC0	10	192.168.10.1	255.255.255.0	FastEthernet0/1<br>
PC1	10	192.168.10.2	255.255.255.0	FastEthernet0/2<br>
PC2	20	192.168.20.1	255.255.255.0	FastEthernet0/3<br>
PC3	20	192.168.20.2	255.255.255.0	FastEthernet0/4<br>
________________________________________
# Procedure
1.	Open Cisco Packet Tracer and add 4 PCs and 1 Switch.<br>
2.	Connect PC0–PC3 to switch ports FastEthernet0/1 to FastEthernet0/4 respectively.<br>
3.	Assign static IP addresses to each PC as per the IP table.<br>
4.	Enter the Switch CLI and create two VLANs:<br>
o	VLAN 10 for PC0 and PC1<br>
o	VLAN 20 for PC2 and PC3<br>
5.	Assign the respective switch ports to their VLANs.<br>
6.	Use the ping command from PC0 to PC1 (should succeed).<br>
7.	Try pinging from PC0 to PC2 (should fail — different VLANs).<br>
________________________________________
# Commands Used (Switch CLI)
bash<br>
CopyEdit<br>
Switch> enable<br>
Switch# configure terminal<br>

Switch(config)# vlan 10<br>
Switch(config-vlan)# name STAFF<br>
Switch(config-vlan)# exit<br>

Switch(config)# vlan 20<br>
Switch(config-vlan)# name STUDENTS<br>
Switch(config-vlan)# exit<br>

Switch(config)# interface range fastethernet0/1 - 2<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 10<br>
Switch(config-if-range)# exit<br>

Switch(config)# interface range fastethernet0/3 - 4<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 20<br>
Switch(config-if-range)# exit<br>
________________________________________
# Output (Screenshots)
•	VLAN configuration on switch<br>
<img width="1482" height="870" alt="image" src="https://github.com/user-attachments/assets/356344ee-baa0-4a83-b35b-a993fbc1307e" />


•	PC IP settings<br>
<img width="1540" height="687" alt="image" src="https://github.com/user-attachments/assets/de5e9634-3adc-41d1-991e-d3517953a106" />

<img width="1651" height="763" alt="image" src="https://github.com/user-attachments/assets/86275e91-7c32-4edb-be6e-b4f5a76bace6" />



•	Successful ping between PCs in the same VLAN<br>
<img width="1662" height="907" alt="image" src="https://github.com/user-attachments/assets/992947bf-a905-4b11-a8a6-c64893f2c791" />
<img width="1827" height="922" alt="image" src="https://github.com/user-attachments/assets/4dd0ba20-8bd1-4f74-b0ef-a9390d14ccba" />



•	Failed ping between PCs in different VLANs<br>
<img width="1681" height="803" alt="image" src="https://github.com/user-attachments/assets/0f841f52-82c0-418a-9849-ec52d83bcc5b" />

________________________________________
# Result
Successfully created and configured VLANs on a managed switch. Verified that only PCs within the same VLAN could communicate with each other.

