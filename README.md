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
- Lab environment for penetration testing tools

<h3>⚙️Tools & Software</h3>

- UniFi Controller (self-hosted)

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


<img src="https://i.imgur.com/LpX5IxT.png">






<h3>Set Up UniFi Console</h3>


- Go to Unifi Site Manager
- Log in, set location name (e.g., "Homelab")
- Adopt your UCG Ultra and USW Lite PoE if not already adopted
- Ensure they're updated to latest firmware
- Change IP address and Set Static IPs
- Configure AP


<h3>Change IP address and Set Static IPs</h3>


<img src="https://i.imgur.com/mp970Cm.png">

<h3>Switch Static IP</h3>


<img src="https://i.imgur.com/03PsMI0.png">

<h3>AP Static IP</h3>


<img src="https://i.imgur.com/gGszXEO.png">


<h3>AP Configurations</h3>


<img src="https://i.imgur.com/e8zrIgJ.png">






<h3>Create VLANs</h3>
VLAN	Name	ID	Subnet	Purpose


- 1 Management (1)	10.25.7.0/24	UniFi router, switch
- 20 Surveillance	(20) 10.25.10.0/24 Security Cameras
- 30 IoT	(30)	10.25.11.0/24	IoT devices
- 40 Guest	(40)	192.168.2.0/24	Visitors
- 50 Home Office (50) 10.25.12.0/24	Work PC
- 60 Sandbox (60) 10.25.13.0/2




<h3>Add VLAN Networks</h3>


- Go to UniFi Console > Settings > Networks
- Click Create New Network
- Name: IoT, VLAN ID: 30, Subnet: 10.25.11.0/24, DHCP: Enabled
- Repeat for each VLAN you want
- Apply VLANs to the respected switch ports matching the connections


<img src="https://i.imgur.com/dIu6CLu.png">





<h3>Create Wifi Network</h3>


- Create name, password
- Select IoT Network
- Make sure 2.4Ghz, 5Ghz is checked
- Select WPA2/WPA3 as the Security Protocol


<h3>Firewall Configurations</h3>


- Go to the gear icon and click on the security tab
- Click protection
- Turn on Intrusion Prevention
- Select your networks
- Click Notify and Block as your detection mode
- Make sure all detections are active


<h3>Traffic and Firewall Rules</h3>

<h4>Block Communication Between VLANs</h4>


- Click LAN
- Click LAN In
- Create entry
- Make sure you select LAN In
- Name this rule something easily recognizable
- Select all protocols
- Select source network(VLAN)
- Select destination network(VLAN)
- Repeat for however many VLANs you have

  For me I have 4 VLANs that I don't want communicating with each other.

<img src="https://i.imgur.com/MK4AneL.png">

<h3>HomeLab Topology</h3>

<img class="image-placeholder" src="https://i.imgur.com/dE84yxk.png" alt>

There you go a fully functional homelab with Unifi Hardware.




