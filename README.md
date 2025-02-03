<h1>HomeLab w/ UniFi Technologies

<h2>Description</h2>
<p align="center">
Installed the UniFi Cloud Gateway Ultra, USW Lite 8 Port PoE Switch and U6+ Access Point.
</p>
<img src="https://i.imgur.com/WehesNu.png">
<p align="center"

Log in to the AT&T Gateway by entering its IP address (192.168.1.254) and your credentials, then enable IP Passthrough mode under LAN settings, disabling the DHCP Server to prevent conflicts. Assign the UniFi Cloud Gateway Ultra (or another device) to receive the public IP address from the AT&T Gateway and connect it to the LAN port.
</p>
<img src="https://i.imgur.com/JrtSJP4.png">
<p align="center">
Connect the UniFi Cloud Gateway Ultra’s WAN port to the AT&T Gateway’s LAN port using an Ethernet cable. Then, access the UniFi Network Controller, log in, and complete the setup wizard to configure the gateway, ensuring it obtains a public IP from the AT&T Gateway and has internet access.
<img src="https://i.imgur.com/glNl3In.png">

<p align="center"

Connect one of the LAN ports on the UniFi Cloud Gateway Ultra to the uplink port on the UniFi Lite 8-Port Switch using an Ethernet cable. In the UniFi Network Controller, ensure the switch is detected, and if not, manually add it and configure it to "Managed" mode for centralized control. Connect a LAN port on the UniFi Lite 8-Port Switch to the Ethernet port on the UniFi Access Point, ensuring PoE is enabled. In the UniFi Network Controller, adopt the Access Point, configure the SSID, Wi-Fi security, and other settings to set up your wireless network.

<img src="https://i.imgur.com/BAly5ZS.png">
<p align="center"
  
Ensure each device has internet access and enjoy the simplicity of UniFi technologies.
</p>
<img src="https://i.imgur.com/nuNZZ62.png">



