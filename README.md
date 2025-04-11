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

<h3>🛠️Adopt Devices in UniFi Network Console</h3>


<h3>Set Up UniFi Console</h3>


- Go to Unifi Site Manager
- Log in, set location name (e.g., "Homelab")
- Adopt your UCG Ultra and USW Lite PoE if not already adopted
- Ensure they're updated to latest firmware


<h3>Create VLANs</h3>
VLAN	Name	ID	Subnet	Purpose

- 10	Management	10	192.168.10.0/24	UniFi devices, switches
- 20	Servers	20	192.168.20.0/24	Proxmox, VMs
- 30	IoT	30	192.168.30.0/24	Smart plugs, cameras
- 40	Guest	40	192.168.40.0/24	Visitors
- 50	Default LAN	1	192.168.1.0/24	General-use devices

<h3>Add VLAN Networks</h3>


- Go to UniFi Console > Settings > Networks
- Click Create New Network
- Name: Servers, VLAN ID: 20, Subnet: 192.168.20.1/24, DHCP: Enabled.
- Repeat for each VLAN you want

<h3>Configure Firewall Rules</h3>
<h4>Set Firewall Rules Between VLANs</h4>


- Go to Settings > Firewall > Rules > LAN IN
- Create rules like:

Block IoT from talking to everything else:
- Name: Block IoT to LAN'
- Action: Drop
- Source: 192.168.30.0/24
- Destination: 192.168.0.0/16

Allow Management access to everything:
- Name: Allow Mgmt
- Action: Accept
- Source: 192.168.10.0/24
- Destination: Any

Block Guest from internal VLANs:
- Block 192.168.40.0/24 to 192.168.0.0/16 (except internet)

<h3>Assign VLANs to Ports and SSIDs</h3>
<h4>Assign VLANs to Switch Ports</h4>

- Go to Devices > USW Lite PoE > Ports
Edit each port:
- Set port profile to match VLAN (e.g., Servers, IoT)
- Use “All” or “Trunk” for access ports to VMs or APs.


<h4>Create SSIDs for VLANs (Wi-Fi)</h4>


- Go to WiFi > Add New WiFi Network
- Name: IoT
- VLAN ID: 30
- WPA2 password: Your choice
Repeat for each VLAN you want wireless access to


<h3>🔒 PART 7: (Optional) Security Add-ons</h3>


- Enable IPS/IDS under Firewall > Threat Management (for UCG Ultra)
- Use Geo-blocking for certain VLANs (like IoT)

There you go a fully functional homelab with Unifi Hardware.




