<h1>HomeLab Project💻

<h3>Project Objective</h3>
The objective for this project is to design and implement a secure, segmented, and scalable home network using enterprise-grade UniFi hardware, enabling hands-on experience in network security, traffic management, and real-world cybersecurity practices.
<h3>Cables and Infrastructure</h3>


- UCG Ultra Gateway
- USW Lite 8 PoE Switch
- Unifi U6+ Access Point
- 5 Cat6A RJ45 Ethernet Cables

<h3>🔒Security Focus Areas</h3>

- VLAN segmentation and firewall rules
- IDS/IPS using UniFi threat management
- Encrypted remote access with VPN
- Lab environment for penetration testing tools

<h3>⚙️Tools & Software</h3>

- UniFi Controller (self-hosted)
- Wireshark

<h3>Setup BGW320-500 to Passthrough Mode</h3>
You want the UniFi Gateway to act as your main router/firewall

- Go to http://192.168.1.254 from a computer connected to the BGW
- Log in (password on the device label)
- Go to Firewall > IP Passthrough
- Set: Allocation Mode: Passthrough
- Passthrough Mode: DHCPS-fixed
- Choose your UCG Ultra's MAC address
- Save and reboot BGW320 and UCG Ultra
- Now UCG Ultra gets the public IP and handles routing/firewall


<img src="https://i.imgur.com/A1dlMpJ.png">

<h3>🛠️Adopt Devices in UniFi Network Console</h3>






<h3>Set Up UniFi Console</h3>


- Go to Unifi Site Manager
- Log in, set location name (e.g., "Homelab")
- Adopt your UCG Ultra and USW Lite PoE if not already adopted
- Ensure they're updated to latest firmware
- Change IP address and Set Static IPs
- Configure AP


<h3>Change IP address and Set Static IPs</h3>



<h3>Switch Static IP</h3>

<h3>AP Static IP</h3>


<h3>AP Configurations</h3>




<h3>Create VLANs</h3>
VLAN	Name	ID	Subnet	Purpose





<h3>Add VLAN Networks</h3>


- Go to UniFi Console > Settings > Networks
- Click Create New Network
- Name: IoT, VLAN ID: 30, Subnet: 10.25.11.0/24, DHCP: Enabled
- Repeat for each VLAN you want
- Apply VLANs to the respected switch ports matching the connections




<h3>Create Wifi Network</h3>


- Create name, password
- Select IoT Network
- Make sure 2.4Ghz, 5Ghz is checked
- Select WPA2/WPA3 as the Security Protocol




<h3>🔒 PART 7: Security Add-ons</h3>


- Enable IPS/IDS under Firewall > Threat Management (for UCG Ultra)
- Use Geo-blocking for certain VLANs (like IoT)

There you go a fully functional homelab with Unifi Hardware.




