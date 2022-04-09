< [Home](https://github.com/SeanOhAileasa) | [README](https://github.com/SeanOhAileasa/nkp-network-concepts/blob/main/README.md) >

## CompTIA Network+ - Course Material 2022

CompTIA Network+ self-study course material.

Can view the ``Jupyter Notebooks`` as a static HTML page on GitHub.

Unfortunately, GitHub may not fully render the ``Jupyter Notebook``.

Recommend viewing using the ``nbviewer`` links below (click on the associated ``render nbviewer`` badge).

### Topic: 

#### ``Network Concepts``

##### ``Ports and Protocols``

<details close>
	<summary>Introduction to IP</summary>

- A Series of Moving Trucks <br/>
	- Road <br/>
		- Network Topology (Ethernet - DSL - Cable System) <br/>
	- Truck <br/>
		- Internet Protocol (IP) <br/>
			- OSI Layer 3 <br/>
				- Network <br/>
					- Routing Layer (IP Address - Router - Packet) <br/>
			- Ethernet Network <br/>
				- Ethernet Header <br/>
				- Ethernet Payload <br/>
					- IP Traffic <br/>
						- IP Payload <br/>
							- TCP (or UDP) [OSI Layer 4 - Transport] <br/>
								- TCP Payload <br/>
									- HTTP Data (ex. Web Browsing) <br/>
				- Ethernet Trailer <br/>
				![Image: Ethernet Network](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ip-protocol-ethernet-network.png?raw=true) <br/>
	- Box <br/>
		- Encapsulated - Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) <br/>
			- Multiplexing <br/>
				- Use Multiple Applications Simultaneously
		- Transmission Control Protocol (TCP) <br/>
		![Image: UDP](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/tcpiposi.png?raw=true) <br/>
			- Connection-oriented <br/>
				- Acknowledgement (``ACK``) <br/>
			- Reliable Delivery <br/>
				- Numbers the Data Sent <br/>
			- Flow Control <br/>
			![Image: TCP](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/tcp-data-ack.png?raw=true) <br/>	
		- User Datagram Protocol (UDP) <br/>
			- Connectionless <br/>
			- Unreliable Delivery <br/>
				- No Error Recovery <br/>
				- No Reording of Data or Retransmissions <br/>
			- No Flow Control <br/>
				- Sender determines amount of Data Transmitted <br/>
				![Image: UDP](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/udp-data.png?raw=true) <br/>			
		- Ports (Written on Box) <br/>
			- IPv4 Sockets <br/>
				- Information Sent <br/>
					- Server IP Address <br/>
						- Protocol (TCP or UDP) <br/>
							- Server Application Port Number <br/>
					- Client IP Address <br/>
						- Protocol (TCP or UDP) <br/>
							- Client Prot Number <br/>
			- Groups <br/>
				- Non-ephemeral (Non-Temporary - Permanent) <br/>
					- Server ("well known") <br/>
						- ``0 - 1023`` <br/>
				- Ephemeral (Temporary) <br/>
					- Client (Real-time) <br/>
						- ``1024 - 65535`` <br/>
			- TCP and UDP Ports Numbers 
				- ``0 - 65535`` <br/>
					- No Conflict <br/>
	- Data <br/>
		- Application <br/>
			- TCP versus UDP <br/>
	- Internet Control Message Protocol (ICMP) <br/>
		- Administration <br/>
			- Carried by IP <br/>
				- Not used for Data Transfer <br/>
					- Text Messaging between Devices (ex. Time-To-Live Expired) <br/>
</details>

<details close>
	<summary>Common Ports</summary>

- Telecommunication Network (Telnet) ``tcp/23`` <br/>
- Secure Shell (SSH) ``tcp/22`` <br/>
- Domain Name System (DNS) ``udp/53`` <br/>
- [Email Transfer] Simple Mail Transfer Protocol (SMTP) ``tcp/25``  <br/>
	- (Email Receive: IMAP4 ``tcp/143`` - POP3 ``tcp/110``) <br/>
- Secure File Transfer Protocol (SFTP) ``tcp/22``  <br/>
	- (Encrypted SSH Protocol as the underlying communication) <br/>
- File Transfer Protocol ``tcp/20`` (active mode data) ``tcp/21`` (control) <br/>
- Trival File Transfer Protcol ``udp/69``	 <br/>
- Dynamic Host Configuration Protocol (DHCP) ``udp/67`` ``udp/68`` <br/>
- Hypertext Transfer Protocol (HTTP) ``tcp/80``  <br/>
	- Hypertext Transfer Protocol Secure (HTTPS) ``tcp/443`` <br/>
- Simple Network Management Protocol (SNMP) ``udp/161`` <br/>
- Remote Desktop Protocol (RDP) ``tcp/3389`` <br/>
- Network Time Protocol (NTP) ``udp/123`` <br/>
- Session Initiation Protocol (SIP) ``tcp/5060`` ``tcp/5061`` <br/>
- Server Message Block (SMB) ``tcp/445`` <br/>
	(Common Internet File System - CIFS) <br/>
- [Email Receive] Post Office Protocol v3 (POP3) ``tcp/110`` <br/>
	- [Email Receive] Internet Message Access Protocol v4 (IMAP4) ``tcp/143`` <br/>
- Lightweight Directory Access Protocol (LDAP) ``tcp/389`` <br/>
	- Lightweight Directory Access Protocol Secure (LDAPS) ``tcp/636`` <br/>
- H.323 ``tcp/1720`` <br/>
</details>

##### ``The OSI Model``

<details close>
	<summary>Understanding Open Systems Interconnection (OSI) Model</summary>

- OSI Protocol Suite (OSI Model built based on these OSI Protocols) <br/>
	- Guide [thus the term "Model"] <br/>
		- The OSI Model <br/>
			- Layer 1 Physical Layer [``!=``Protocols] <br/>
				- Network Physics [Signaling / Cabling / Connectors] - [NIC - Cable - Hub] <br/>
					- Problems <br/>
						- Fix Cabling - Punch-downs <br/>
						- Run Loopback Test - Test and/or replace Cables - Swap Adapter Cards <br/>
			- Layer 2 Data Link Layer ["switching"] - [Frame - MAC Address - EUI-48 - EUI-64 - Switch] <br/>
				- Network Basic Language [Foundation of Communication] <br/>
				- Data Link Control (DLC) Protocols <br/>
					- Media Access Control (MAC) Address on an Ethernet Network <br/>
			- Layer 3 Network Layer ["routing"] - [IP Address - Router - Packet] <br/>
				- Internet Address (IP) <br/>
					- Fragments Frames [Traverse different Networks]
					- IP Fragmentation <br/>
						- Multiples of ``8``
							- No. Fragmentation offset bits in IP Header <br/>
			- Layer 4 Transport Layer ["post office"] - [TCP Segment - UDP Datagram] <br/>
				- Parcels & Letters <br/>
				- Transmission Control Protocol (TCP) or User Datagram Protocol (UDP) <br/>
			- Layer 5 Session Layer - [Control Protocols - Tunnelling Protocols] <br/>
				- Communication Management between Devices [Start / Stop / Restart] <br/>
					- Duplex [Full / Half] <br/>
			- Layer 6 Presentation Layer [Often combined with Application Layer] - [SSL / TLS] <br/>
				- Character Encoding <br/>
				- Application Encryption <br/>
			- Layer 7 Application Layer [User Sees] <br/>
				- HTTP <br/>
				- FTP <br/>
				- DNS <br/>
				- POP3 <br/>
	        ![Image: OSI Model](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/osi-model.png?raw=true) <br/>			
			- Wireshark <br/>
</details>

##### ``Routing and Switching``

<details close>
	<summary>Introduction to Ethernet</summary>

- Small Office/Home Office (SOHO) Local Area Network (LAN) <br/>
- Enterprise Network <br/>
- Ethernet Frame [Packet Analyser] <br/>
	- Preamble [``7`` bytes] <br/>
		- ``101010...`` <br/>
	- Start Frame Delimiter (SFD) [``1`` byte] <br/>
		- ``1010101011`` <br/>
	- Destination MAC Address [``6`` bytes] <br/>
	- Source MAC Address [``6`` byte] <br/>
	- Type [EtherType] - [``2`` bytes] <br/>
	- Payload - [``46-1500`` bytes] <br/>
		- IP - TCP (or UDP) <br/>
	- Frame Check Sequence (FCS) <br/>
		- CRC - Checksum of Frame <br/>
- Media Access Control (MAC) Address <br/>
	- Physical Address of Network Adaptor <br/>
		- Unique to a Device <br/>
	- 48-bits [``6`` bytes] - [Hexadecimal] <br/>
		- Organisationally Unique Identifier (OUI) [1st Half] <br/>
			- Manufacturer <br/>
		- Network Interface Controller-Specific [2nd Half] <br/>
			- Serial No. <br/>
- Connect Ethernet Device to a Network <br/>
	- Configuration Parameters <br/>
		- Duplex <br/>
			- Half-duplex <br/>
				- Device ``!=`` Send/Receive Simultaneously <br/>
					- Send Only or Receive Only <br/>
				- Hub - [All Traffic to All Devices] <br/>
					- Communicate Simultaneously <br/>
						- Frames create a Collision <br/>
							- Wait Random Time <br/>
								- Retry Communication <br/>
						- CSMA/CD [``!=`` Used Today] <br/>
							- CS (Carrier Sense) <br/>
								- Ethernet Adaptor Listens for available Carrier <br/>
									- Send Frame to Network <br/>
							- MA (Multiple Access) <br/>
								- ``>1`` Devices on Network <br/>
							- CD (Collision Detect) <br/>
								- Communicate Simultaneously [Collision] <br/>
									- Identify Collision <br/>
										- Transmit a Jam Signal [Everyone Knows] <br/>
										- Wait Random Time <br/>
				- Switch Interfaces <br/>
					- Usually only when Connecting another Half-duplex Device <br/>
			- Full-duplex  <br/>
				- Device ``==`` Send/Receive Simultaneously <br/>
					- Switch + Endstation Configured Correctly <br/>
				- Switch Interface <br/>
					- Determines Intelligently Traffic <br/>
						- Source creates Ethernet Frame [MAC Address] <br/>
							- Frame to Switch <br/>
								- Lookup Function [MAC in Table] <br/> 
				- Wireless  <br/>
					- CSMA/CA (Collison Avoidance) <br/>
						- Collision Detection not Possible <br/>
							- Sending Station <br/>
								- ``!=`` "hear" other Station <br/>						 
						- Hidden Node Problem <br/>
							- Station A can hear the Access Point <br/>
								- Station B can hear the Access Point <br/>
									- Station A cannot hear Station B <br/>
						- Send Data <br/>
							- Ready to Send (RTS) <br/>
								- "I'm Ready" <br/>
							- Clear to Send (CTS) <br/>
								- "You're Clear" <br/>
</details>

<details close>
	<summary>Network Switching Overview</summary>

- Switching <br/>
	- Forwarding or Dropping Frames  <br/>
		- Based on Destination MAC Address <br/>
	- Constantly Update [Table - from Source] <br/>
		- MAC Addresses <br/>
		- Associated Interfaces <br/>
	- Prevent Network Loops  <br/>
		- Spanning Tree Protocol (STP) <br/>
- Frame Switching <br/>
	- Fast Ethernet ``F``  <br/>
		- Slot (Card) ``F#``  <br/>
			- Interface (Device) ``F#/#`` [MAC Address] <br/>
	- Table [within Switch] <br/>
		- List of seen MAC Addresses <br/>
		- List of associated Output Interfaces <br/>
- Frame Switching between Switches <br/>
	- Independent Table (each Switch) <br/>
		- List of MAC Addresses <br/>
		- List of Output Interfaces <br/>
- Learn the MACs (Incoming Traffic - Note Source) <br/>
	- Flooding Unknown MACs <br/>
		- Send Frame to All <br/>
	- No Flooding of MACs <br/>
- Address Resolution Protocol (ARP) <br/>
	- Broadcast [Determine MAC Address based on IP Address] <br/>
		- Packet Analyzer <br/>
		- Command Line ``arp -a`` <br/>
</details>

<details close>
	<summary>Collision Domains and Broadcast Domains</summary>

- Collision Domains [Half-duplex Networks] <br/>
	- Collision [Hub] <br/>
		- Normal Process (Network Communication) <br/>
	- CSMA/CD <br/>
		- Carrier Sense Multiple Access (CSMA) <br/>
			- Network Stations Listening <br/>
				- Determine if able to Communication <br/>
		- Collison Detection (CD) <br/>
			- Network Stations recognise Collision Occurred <br/>
				- Clear Network [Sending Jam Signal] <br/>
					- Retransmit <br/>
	- Historial Footnote [One Big Segment] <br/>
		- Coax Network <br/>
			- Stations Connected on same Cable <br/>
		- Ethernet Hub <br/>
			- Stations Connected to Central Device <br/>
	- Segment different Networks (Segment out Collision Domains) <br/>
		- Switch (or Bridge) <br/>
			- Each side of Switch a different Collision Domain <br/>
	- Modern Footnote <br/>
		- Switch (Collision Domains Removed) <br/>
			- Full-duplex <br/>
				- Stations can Send / Receive Simultaneously <br/>
					- No Concern of a Collision <br/>
					![Image: Collision Domains](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/collision-domains.png?raw=true) <br/>
- Broadcast Frames (Different to Collisions) [Necessary Evil] <br/>
	- Send Broadcast Address <br/>
		- Spread the Word (All must Know) <br/>
			- Address Resolution Protocol (ARP) Requests <br/>
			- Operating System Notifications <br/>
			- Some Dynamic Routing Protocols <br/>
				- Advertise Available Network Routes <br/>
- Broadcast Domains <br/>
	- Switch Network [Switch / Bridge] <br/>
		- All See Broadcast <br/>
	- Router <br/>
		- Separating Network <br/>
			- Block Broadcast <br/>
	- Segment Network 
		- Segmenting Broadcasts [Particular Broadcast Domain] <br/>
		![Image: Broadcast Domains](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/broadcast-domains.png?raw=true) <br/>
</details>

<details close>
	<summary>Unicasts and Broadcasts and Multicasts</summary>

- Unicast [One Station to One Station] <br/>
	- One-to-One Relationship <br/>
		- Web Browsing Session <br/>
		- File Transfers <br/>
	- Scale Issues <br/>
		- Not Optimal for Streaming Media <br/>
- Broadcast [One Station to All at Once] <br/>
	- Broadcast Domain [Limit Scope - Subnet] <br/>
		- Routing Updates & OS Communication <br/>
		- IPv4 <br/>
			- Address Resolution Protocol ``ARP`` Request <br/>
		- Broadcast Frames <br/>
			- Slow Network Performance <br/>
		- IPv6 [``!=`` Broadcast] <br/>
			- Multicast [Compromise between Unicast & Broadcast] <br/>
				- One-to-Many Relationship [Delivery to Interested Systems] <br/>
					- Multimedia Delivery <br/>
					- Stock Exchanges <br/>
				- Specialised [Limited Scope] <br/>
					- Scale Issues <br/>
						- Infrastructure Devices <br/>
							- Understand Multicast <br/>
						- End-devices <br/>
							- Subscribe / View Multicast Information] <br/>
</details>

<details close>
	<summary>Protocol Data Unit (PDU)</summary>

- Unit of Information (Transmission) [Sent at a particular OSI Layer] <br/>
	- Switch <br/>
		- PDU <br/>
			- Ethernet <br/>
				- Frame of Data [No Knowledge of its Contents] <br/>
	- IP <br/>
		- PDU <br/>
			- Packet of Data <br/>
	- TCP <br/>
		- PDU <br/>
			- TCP Segment <br/>
	- UDP <br/>
		- PDU <br/>
			- UDP Datagram <br/>
- Source to Destination <br/>
	- Encapsulation <br/>
		- OSI Layer [7, 6, & 5] <br/>
			- Data Associated with Application <br/>
		- OSI Layer [4]  <br/>
			- Add TCP Header <br/>
				- PDU Included (within TCP Packet) [Contains Application Information] <br/>
		- OSI Layer [3]  <br/>
			- Add IP Header <br/>
				- PDU Included [Contains TCP Header & Application Information]
		- OSI Layer [2] <br/>
			- MAC Addresses (Encapsulate Data Link Frame) <br/>
		- OSI Layer [1]  <br/>
			- Send Across the Network <br/>
	- Decapsulation [Frame on other side of Network] <br/>
		- OSI Layer [2] <br/>
			- Data Link Frame <br/>
				- Strip off Headers [Frame Header / IP Header / TCP Header] <br/>
					- Application PDU for Destination <br/>
					![Image: PDU](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/pdu-encapsulation-decapsulation.png?raw=true) <br/>
- Maximum Transmission Unit (MTU) <br/>
	- Determines Maximum Size of IP Fragment sent across Network <br/>
		- Without Fragmenting the Data <br/>
	- Fragmentation [Negative Impact on Communication Efficiency] <br/>
		- Takes Time [Fragment Packet into Smaller Pieces] <br/>
		- Lose Fragments [Loses Entire Packet] <br/>
			- Retransmit all Fragments <br/>
		- Sometimes Do Not Know its Happening <br/>
			- MTU Size Unknown [One End of Network to the Other] <br/>
				- Commonly Automated when Session is Established <br/>
					- Internet Control Message Protocol (ICMP) Filtered [Often Inaccurate] <br/>
						- Requiring Manual Configuration [MTU Values] <br/>
		- Build Ethernet Frame (Fragmentation affects the Information) <br/>
			- TCP Data [1460 bytes]  <br/>
				- TCP Header [20 bytes] <br/>
					- IP Header [20 bytes] <br/>
			- Wrap Ethernet  <br/>
				- [14 bytes - Header] <br/>
				- [4 bytes - Frame Check Sequence FCS] <br/>
			- Tunnel over Different Connection [VPN] <br/>
				- Hit Maximum Size (Ethernet Frame) [1500 bytes] <br/>
					- Fragment Data before sending through Tunnel <br/>
					![Image: Build Ethernet Frame](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/build-ethernet-frame.png?raw=true) <br/>
						- Fragments always mulitiples of ``8`` [# of Fragmentation Offset bits in IP Header] <br/>
	- Troubleshooting <br/>
		- Size usually Configured Once (not changed often) [Network Infrastructure Based] <br/>
		- Concern for Tunneled Traffic [VPN] <br/>
			- Additional Headers [Around the IP Information] <br/>
				- Now too Large for Ethernet Network [Requiring Fragmentation] <br/>
		- Applications that do not want its Data Fragmented <br/>
			- Don't Fragment (DF) <br/>
				- Special bit in IP Header [Do Not Fragment] <br/>
					- Message through Internet Control Message Protocol (ICMP) [DF Set] <br/>
			- Configure MTU [Without Fragmentation] <br/>
				- ``ping`` [Start with Maximum Size of ``1500`` bytes - Keep Lowering] <br/>
					- Maximum size of IP Packet [ICMP Header (``8`` bytes) & IP Header (``20`` byte) = ``1472``] <br/>
						- ``ping -f -l 1472 <ip address>`` [Windows] <br/>
							- ``-f`` <br/> 
								- ``!=`` Fragment <br/>
							- ``-l`` <br/>
								- Specify Link [``1472``] <br/>
							- ``<ip address>`` <br/>
								- Device on other side of the Communication <br/>
</details>

<details close>
	<summary>Network Segmentation</summary>

- Local Area Network <br/>
	- Physical <br/>
		- Group of Devices in the same Broadcast Domain <br/>
			- Switches (x2) <br/>
				- Broadcast Domains (x2) [Devices not aware of other Switches] <br/>
					- Segmentation via Physical Devices [No VLAN] <br/>
						- Difficult to Scale <br/>
						![Image: Devices in Same Broadcast Domain (Physical)](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/physical-segmentation.png?raw=true) <br/>
	- Logical [Segmentation within Switch] <br/>
		- Virtual LAN (VLAN) [Separated Logically] <br/>
		![Image: Devices in Same Broadcast Domain (Logical)](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/logical-segmentation.png?raw=true) <br/>
			- Configuration <br/>
				- Multiple Switches <br/>
					- Trunk [Physical Connection between Switches] <br/>
						- Transmit Multiple VLANs across Trunk <br/>
							- Standard ``802.1Q`` [``.1Q`` Trunk] <br/>
							![Image: VLAN Trunking](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/trunk.png?raw=true) <br/>
		- Ethernet Frame [Normal Frame] <br/>
			- Packet Analyser <br/>
				- Preamble [``7`` bytes] <br/>
					- ``101010...`` <br/>
				- Start Frame Delimiter (SFD) [``1`` byte] <br/>
					- ``1010101011`` <br/>
				- Destination MAC Address [``6`` bytes] <br/>
				- Source MAC Address [``6`` byte] <br/>
				- Type [EtherType] - [``2`` bytes] <br/>
				- Payload - [``46-1500`` bytes] <br/>
					- IP - TCP (or UDP) <br/>
				- Frame Check Sequence (FCS) <br/>
					- CRC - Checksum of Frame <br/>	
			- Identify Frame Source & Destination [Fit VLAN Information within Frame] <br/>
				- Add VLAN Field [Sending Information over Trunk] <br/>
					- VLAN Header [Specify Destination VLAN] <br/>
						- Packet Analyser [``12`` bits = 4094 VLANs] <br/>
						- Cisco Switches <br/>
							- Normal Range [``1`` to ``1005``] <br/>
							- Extended Range [``1006`` to ``4094``] <br/>
						- Other Switches [``1`` to ``4094``] <br/>
						- Reserved VLAN Numbers [``0`` & ``4095``] <br/>
							- Cannot Specify as separate VLANs on Switch <br/>
			- Trunking Process <br/>
				- Information sent to the ``.1Q`` Interface <br/>
					- Add VLAN Information to the Frame <br/>
						- Sent across Trunk <br/>
				- Other Side VLAN Tag taken out of Frame <br/>
					- Sent to appropriate VLAN <br/>
			- Trunk [No Longer Used]  <br/>
				- Inter-Switch Link (ISL) <br/>
</details>

<details close>
	<summary>Spanning Tree Protocol</summary>

- Ethernet Switches [Connect via Single Cable] <br/>
	- Second Cable [Creates Loop between both Switches] <br/>
		- No Counting Mechanism at the MAC Layer [Until Cable Pulled out of a Switch] <br/>
			- Sending Traffic back and forth Forever <br/>
				- Break Network <br/>
- Loop Protection <br/>
	- Spanning Tree Protocol (STP) <br/>
		- Standards <br/>
			- ``802.1D`` <br/>
		- Prevent Loops (Bridged [Switched] Networks) <br/>
			- MAC Layer <br/>
		- Port Configured to use STP <br/>
			- States <br/>
				- Blocking <br/>
					- ``!=`` Forwarding to Prevent Loop <br/>
				- Listening <br/>
					- ``!=`` Forwarding & Cleaning the MAC Table <br/>
				- Learning <br/>
					- ``!=`` Forwarding & Adding to the MAC Table <br/>
				- Forwarding <br/>
					- Data Passes Through (Fully Operational) <br/>
				- Disabled <br/>
					- Administrator Turns Off Port <br/>
		- Configured (Automatically - May take Longer Path Traversal) Interfaces <br/>
			- Root Switch [x1 on any STP Network] <br/>
				- Root Port (RP) <br/>
					- Other Switches [Interface closest to Root Switch designated Root Port] <br/>
						- Allows Traffic to Traverse Particular Interface <br/>
							- Other Interface <br/>
								- Traffic Allowed to Traverse <br/>
									- Designated Port (DP) <br/>
							- Port STP Disabled [Prevent Loop] <br/>
								- Blocked Port (BP) <br/>
								![Image: STP Network](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/stp-network.png?raw=true) <br/>
		- Switch Fails or Link Disconnected <br/>
			- Converge Network & Restructure Devices [Reconfigure through STP] <br/>
				- Maintains Loop Free Environment <br/>
					- Convergence Process [Network Back] <br/>
						- ``30`` to ``50`` Seconds <br/>
				![Image: Switch or Link Fails then STP Reconfigures](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/link-broken-stp-reconfigure.png?raw=true) <br/>
	- STP Updated <br/>
		- Rapid Spanning Tree Protocol (RSTP) <br/>
			- Standard <br/>
				- ``802.1w`` <br/>
					- Convergence Process [Network Back] <br/>
						- 	``6`` Seconds <br/>
					- Backwards-compatible with ``802.1D`` STP [Mix in Network] <br/>
					- Update not Wholesale Change <br/>
</details>

<details close>
	<summary>Switch Interface Properties</summary>

- Interface Configuration <br/>
	- Ethernet <br/>
		- Speed [10 / 100 / 1000 or Faster Ethernet] & Duplex [Half / Full] <br/>
			- Setting must Match at both Sides [Automatic or Manual] <br/>
		- IP Address [Particular Interface] <br/>
			- Layer 3 Interfaces [on a Router] <br/>
			- VLAN Interfaces [Access to particular VLAN on a Switch] <br/>
			- Management Interfaces <br/>
			- Workstation <br/>
				- IP Address <br/>
				- Subnet Mask / CIDR Block <br/>
				- Default Gateway <br/>
				- DNS (Optional) <br/>
	- Switch <br/>
		- VLAN Interface [Determine Membership] <br/>
			- Assign VLAN # to Interface Connected to Device [Port assigned a VLAN] <br/>
		- Designated Trunk Interfaces <br/>
			- Specify as a Trunk Interface [Connecting Switches Together] <br/>
			- Specify VLANs allowed to Communicate via Trunk <br/> 
		- Switch Tagged Frame [Information] <br/>
			- VLAN Number <br/>
				- VLAN Tag Removed from Frame on other Side <br/> 
					- Frame Placed on the Proper VLAN <br/>
		- Switch Untagged Frame <br/>
			- Send Management Frames [Common] <br/>
				- Default or Native VLAN <br/>
					- Traffic on particular VLAN ``!=`` Tag Added going across Trunk <br/>
					![Image: Trunk](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/trunk.png?raw=true) <br/>
		- Demilitarised Zone (DMZ) [Additional Layer of Security] <br/>
			- Access from Outside [Access Certain Resources within DMZ] <br/>
				- Prevents Access to Internal Network [Devices] <br/>
				![Image: Demilitarised Zone](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/dmz.png?raw=true) <br/>
		- Ethernet Cable [Switch Power over Ethernet (PoE)] <br/>
			- Data Connection <br/>
				- Power [x1 Wire for Network & Electricity] <br/>
					- Power over Ethernet (PoE) [Power Difficulty due to Location] <br/>
						- VoIP Phone <br/>
						- Wireless Access Point (AP) <br/>
						- Remote Camera [Security] <br/>
					- Switch provides Power [Power over Ethernet (PoE)] <br/>
						- Endspan Power over Ethernet Connection [Built-in Power] <br/>
						- Switch ``!=`` Power over Ethernet (PoE) Capability <br/>
							- Midspan [Power Injector in the Middle of the Communication] <br/>
						- Power Modes [Power over Ethernet (PoE)] <br/>
							- A <br/>
								- Power on same Wires used for Data <br/>
							- B <br/>
								- Spare Wires used for the Power <br/>
						- Specification [PoE] <br/>
							- PoE IEEE ``802.3af-2003`` <br/>
								- Original [Part of ``802.3`` Ethernet Standard] <br/>
								- DC Power [Over PoE Connection] <br/>
									- ``15.4W`` <br/>
									- ``350mA`` [Maximum Current] <br/>
							- PoE+ IEEE ``802.3at-2009`` <br/>
								- Updated [Part of ``802.3`` Ethernet Standard)] <br/>
								- DC Power [Over PoE Connection] <br/>
									- ``25.5W`` <br/>
									- ``600mA`` [Maximum Current] <br/>
	- Port Mirroring <br/>
		- Connect Monitoring Device [Switch Port Analyser (SPAN)] <br/>
			- Traffic Examination [Copy] <br/>
				- Send to Monitoring Device <br/>
		- Intrusion Prevention System (IPS) <br/>
			- Configure IPS Switch [Be a Port Mirror (SPAN Port)] <br/>
				- Create Tapped Connection [Copy] <br/>
					- Data to Destination <br/>
					- Copy of Data sent to IPS <br/>
</details>

<details close>
	<summary>Static and Dynamic Routing</summary>

- Send IP Packets [Across Network] <br/>
	- Forwarding Decisions [Based on Destination IP Address] <br/>
- Routing [Knows the Next Step] <br/>
	- Packet asks for Directions [Every Hop Along the Way] <br/>
		- Directions (Steps) held in a Routing Table <br/>
	- Static Routing [Define List of Available Routes] <br/>
		- Administrator Define the Routes Manually <br/>
			- Advantages <br/>
				- Small/Simple Network [Easier if Statically Routed] <br/>
				- No Overhead from Routing Protocols <br/>
					- CPU <br/>
					- Memory <br/>
					- Bandwidth <br/>
				- Remote Sites [Sub Networks] <br/>
					- One way to send Data <br/>
				- Consider to be Secure  <br/>
					- No Routing Protocols Analysing how Traffic is Forwarded <br/>
			- Disadvanges <br/>
				- Difficult to Administer on Larger Networks <br/>
				- No Automatic Method to prevent Routing Loops <br/>
				- Link down (Network Change) requires Manual Reconfiguration <br/>
					- No Automatic Routing if Outage Occurs <br/>
		- Configuration [x2 Static Routes] <br/>
			- Table Update [Perspective of Particular Router (Router 1)] <br/>
				- Network Address (Sam) [Route] <br/>
					- ``10.10.20.0/24`` [Network of Jack] <br/>
						- Router Address [Next Hop] <br/>
							- ``10.10.40.2/24`` [Hop to Jack] <br/>					
					- ``10.10.30.0/24`` [Network of Teal'c] <br/>
						- Router Address [Next Hop] <br/>
							- ``10.10.50.2/24`` [Hop to Teal'c] <br/>
				![Image: Static Routes](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/static-routes.png?raw=true) <br/>
	- Dynamic Routing <br/>
		- Routers Send Updates [(Almost) Real-time] <br/>
			- Advantages <br/>
				- No Manual Route Calculations or Management <br/>
				- New Routers Populated Automatically <br/>
				- Very Scalable <br/>
			- Disadvantages <br/>
				- Uses bandwidth to send Updates <br/>
					- Overhead Required [CPU - Memory - Bandwidth] <br/>
				- Requires Some Inital Configuration <br/>
		- Configuration [Automatic] <br/>
			- Remote Routers <br/>
				- Send Routing Update [All other Routers] <br/>
					- Receiving Router [Table (Routing) Automatically Updated] <br/>
						- Routing Information Protocol Version 2 (RIPv2) Update <br/>
	- Gateway of Last Resort <br/>
		- Default Route [Special Static Route] <br/>
			- Configured inside Router <br/>
				- No Match <br/>
					- Then Send this Way <br/>
			- Router make no Traffic Routing Decisions <br/> 
				- Remote Site [Common] <br/>
					- Traffic [One-way] <br/>
						- Traffic Inside [Send Traffic Outside] <br/> 
						- Traffic Outside [Send Traffic Inside] <br/>
</details>

<details close>
	<summary>Interior Gateway Protocol (IGP) and Exterior Gateway Protocol (EGP)</summary>

- Interior Vs. Exterior <br/>
	- Autonomous System (AS) <br/>
		- Existing as an Independent Entity [Independent Network] <br/>
			- Group of IP Addresses under Common Control [IP Networks] <br/>
		- Point of Reference <br/>
			- Networks inside of our Control <br/>
			- Networks outside of our Control <br/>
- Interior Gateway Protocol (IGP) <br/>
	- Within Single Automous System (AS) [Internal] <br/>
		- ``!=`` Route between AS [Outside of our Control] <br/>
	- IPv4 [Dynamic Routing Protocols] <br/>
		- Open Shortest Path First Version 2 (OSPFv2) <br/>
		- Routing Information Protocol Version 2 (RIPv2) <br/>
		- Cisco Networks <br/>
			- Enhanced Interior Gateway Routing Protocol (EIGRP) <br/>
	- IPv6 [Dynamic Routing Protocols] <br/>
		- Open Shortest Path First Version 3 (OSPFv3) <br/>
		- Routing Information Protocol next generation (RIPng) <br/>
		- Enhanced Interior Gateway Routing Protocol (EIGRP) for IPv6 <br/>
- Exterior Gateway Protocol [Route Between AS] <br/>
	- Leverages IGP at the AS to handle Local Routing <br/>
	- Border Gateway Protocol (BGP) [Routing Protocol] <br/>
		- Connect to Internet <br/>
- Interior & Exterior Routing <br/>
	- Autonomous System (x4) <br/>
		- Running Protocols <br/>
			- Routing Information Protocol (RIP) <br/>
			- Enhanced Interior Gateway Routing Protocol (EIGRP) <br/>
			- Open Shortest Path First (OSPF) <br/>
			- Routing Information Protocol Version 2 (RIPv2) <br/>
		- Communicate Outside AS <br/>
			- Using Exterior Protocol [Border Gateway Protocol (BGP)] <br/>
				- Internet Connection <br/>
				- All Device [Route from One Side to the Other]  
				![Image: Border Gateway Protocol (BGP)](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/bgp.png?raw=true) <br/>
</details>

<details close>
	<summary>Dynamic Routing Protocols</summary>

- Routing Network [Use a Dynamic Routing Protocol] <br/>
	- Communicates between Routers [Know All Available Routes] <br/>
		- Provide Subnet Information to the Routers <br/>
- Determine Best Path (based on Gathered Information) [Forward Traffic] <br/>
	- Outage (Link Down) Reconverge [Build new Routes] <br/>
		- Update Routes <br/>
			- Every Dynamic Routing Protocol has different Convergence Process <br/>
- Router Determines Traffic Path <br/>
	- List Best Routes to Worst Routes <br/>
		- Distance [Hops] <br/>
			- Algorithm [Formula] <br/>
				- Distance-ventor Routing Protocols <br/>
					- ``#`` of Hops <br/>
						- Vector [Distance] <br/>
					- Usually Automatic <br/>
						- Very Little Configuration <br/>
					- Good for Smaller Networks <br/>
						- ``!=`` Scale to very Larget Networks <br/>
					- Standard <br/>
						- Routing Information Protocol (RIP) <br/>
						- Routing Information Protocol Version 2 (RIPv2) <br/>
						- Enhanced Interior Gateway Routing Protocol (EIGRP) [Cisco] <br/>
					- ``!=`` Speed <br/>
						- Lowest Hops to Destination [Sam: ``R2`` ``R1``] <br/> 
						![Image: Distance-vector Routing](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/distance-vector-routing-protocol.png?raw=true) <br/>
		- Link State [Quality] <br/>
			- Algorithm [Formula] <br/>
				- Link-state Routing Protocols <br/>
					- Connection Quality <br/>
						- Information Passed (Routers) related to current Connectivity <br/>
							- Up [Can Get There] <br/>
							- Down [Cannot Get There] <br/>
					- Considers Speed of Link <br/>
						- Faster Link gets Higher Priorty <br/>
					- Very Scalable <br/>
						- Used most often in Large Networks <br/>
					- Standard <br/>
						- Open Shortest Path First (OSPF) <br/>
					- ``!=`` Distance <br/>
						- Fastest Connection to Destination [Sam: ``R2`` ``R3`` ``R1``] <br/>
						![Image: Link-state Routing](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/link-state-routing-protocol.png?raw=true) <br/>
		- Hybrid Routing Protocols <br/>
			- Combined Distance-vector and Link-state <br/>
				- Border Gateway Protocol (BGP) <br/>
					- Route based on Paths or Network Policies or Configured Rule-sets <br/>
- Environment [Dynamic Routing Protocol to Use] <br/>
	- Convergence [Rebuilding Routes (Outage or Link Down)] <br/>
		- Time <br/>
	- Standard Protocols <br/>
		- Routing Information Protocol (RIP) [Distance-vector] <br/>
		- Open Shortest Path First (OSPF) [Link-state] <br/>
	- Proprietary Protocols <br/>
		- Enhanced Interior Gateway Routing Protocol (EIGRP) [Cisco] <br/>
</details>

<details close>
	<summary>IPv4 and IPv6 Addressing</summary>

- TCP/IP [Network Protocol of Choice] <br/>
	- Devices assigned Unique IP Address <br/>
		- Combined with Subnet Mask <br/>
			- Local Device to Determine what IP Subnet its Lives <br/>
			- Not Transmitted across the Network [Local Device] <br/>
- IP Address [``!=`` Single Address] <br/>
	- Combination of Network ID and Host ID <br/>
		- Subnet Mask Determines (via IP Address) the Network and Host <br/>
			- Just as Important as the IP Address <br/>
	- OSI Layer 3 Addresses <br/>
		- IPv4 (Internet Protocol version 4) <br/>
			- 32-bit Address <br/>
			![Image: IPv4 Address](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ipv4-address.png?raw=true) <br/>
		- IPv6 (Internet Protocol version 6) <br/>
			- 128-bit Address [340 Undecillion] <br/>
			![Image: IPv4 Address](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ipv6-address.png?raw=true) <br/>
			- Compression <br/>
				- Group Zeros [Abbreviated ``::`` (x1 Only)] <br/>
				- Leading Zeros Optional <br/>
				![Image: IPv4 Address](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ipv4-address-compression.png?raw=true) <br/>
</details>

<details close>
	<summary>Configuring IPv6</summary>

- Dual-stack Routing [Common Implementation] <br/>
	- Dual-stack IPv4 & IPv6 [Protocols ``!=`` Talk to Each Other] <br/>
		- Run at the same Time [OSI Layer 3 Device] <br/>
	- IPv4 <br/>
		- Configured with IPv4 Addresses [Subnet Masks / DNS etc] <br/>
		- Maintains an IPv4 Routing Table <br/>
		- Router <br/>
			- Uses IPv4 Dynamic Routing Protocols <br/>
	- IPv6 [Same Device with Separate Configuration Area] <br/>
		- Configured with IPv6 Addresses [Subnet Masks / DNS etc] <br/>
		- Maintains a separate IPv6 Routing Table <br/>
		- Router <br/>
			- Uses IPv4 Dynamic Routing Protocols <br/>	
- ``!=`` Networks Upgraded [Parts with Support for IPv6] <br/>
	- Tunnel IPv4 into IPv6 [IPv6 into IPv4] <br/>
		- ``6to4`` Tunnelling <br/>
			- Send IPv6 over existing IPv4 Network <br/>
				- Requires Relay Routes [Both End of the Communication] <br/>
					- IP Protocol ``41`` [Transition Technology] <br/>
						- Identify Special Packets [Contain IPv6 Information] <br/>
			- ``!=`` Support for Network Address Translation (NAT) <br/>
				- May Apply to Specific Network Configurations [Transition Technology] <br/>
		- ``4in6`` Tunnelling <br/>
			- Existing IPv6 Network Tunnelling IPv4 Traffic <br/>
	- Teredo Tunnel [Windows] <br/>
		- Tunnel IPv6 through Network Address Translated (NAT) IPv4 [Common Configuration] <br/>
			- End-to-end IPv6 through an IPv4 Network <br/>
				- ``!=`` Configurations on IPv4 Routers <br/>
				- ``!=`` IPv6 Router Required <br/>
			- Temporary Workaround until IPv6 can be used Natively on Network (?) <br/>
	- Miredo (Open-source Teredo) [Linux / BSD Unix / MAC OS X] <br/>
		- Same Full Functionality as Teredo <br/>
- Devices Find Devices <br/> 
	- IPv4 Uses Broadcast <br/>
		- IPv6 Uses Multicast [over ICMPv6] <br/>
- Neighbor Discovery Protocol (NDP) [Devices find other Devices] <br/>
	- Stateless Address Autoconfiguration (SLAAC) <br/>
		- Automatically Configures an IP Address without a DHCP Server <br/>
	- Duplicate Address Detection (DAD) <br/>
		- No Duplicate IPs <br/>
	- Discover Routers [ICMPv6 Adds NDP] <br/>
		- Router Solicitation (RS) <br/>
			- Sends IPv6 Multicast [``ff02::2``] <br/>
				- Solicitation to All IPv6 Routers <br/> 
					- Network Routers Listen for these Multicasts <br/>
						- Router Advertisement (RA) [Unicast Frame] <br/>
							- Sends Advertised MAC of Local Router <br/>
							![Image: IPv6 NDP](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ipv6-ndp.png?raw=true) <br/>
							- Occasional Send Unsolicited RA [Multicast ``ff02::1``] <br/>
								- Transfer IPv6 Address Information [to Workstation] <br/>
									- Prefix Value [Network] <br/>
									- Prefix Length [Local Subnet Mask] <br/>
	- IPv6 ``!=`` Address Resolution Protocol (ARP) [IPv4] <br/>
		- Neighbor Media Access Control (MAC) Discovery [Same Function as IPv4 ARP] <br/>
			- Neighbor Solicitation (NS) <br/>
				- Workstation Find MAC of other Workstation <br/>
					- Sends Multicast <br/>
						- Seek Specified MAC Address of IPv6 Address <br/>
							- Neighbor Advertisement (NA) [Owner of IPv6 Address] <br/>
								- Sends Back Directed Frame [Include MAC Address] <br/>
								![Image: IPv6 Discover MAC](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ipv6-discover-mac.png?raw=true) <br/>
				- Test for Duplicate IPv6 Address <br/>
					- Workstation Sends out NS for Specific IPv6 Address <br/>
						- ``!=`` Response then IPv6 Address Available on Network <br/>
</details>

<details close>
	<summary>Prioritizing Traffic</summary>

- Networks Use Different Devices [Different Applications] <br/>
	- Mission Critical Applications [Perform Major Functions of a Particular Job] <br/>
	- Voice over IP (VoIP) <br/>
	- Streaming Video / Audio <br/>
- Different Network Requirements <br/>
	- Voice Communication requires Real-time Data Flows <br/>
	- Watching Streaming Video usually has a Buffer Associated <br/>
	- Database Application usually has Interactive Input <br/>
		- Expecting an Output within a Certain Ammount of Time <br/>
- Might want to Prioritise Traffic Type on the Network <br/>
	- VoIP Traffic having a Priority over YouTube videos <br/>
- Pioritisation through Packet Shaping [Traffic Shaping] <br/>
	- Apply Certain Bandwidth Usages (or Data Rates) to a Particular Type of Application <br/>
		- Able to set Certain Applications to have Higher Priority than Others <br/>
			- May be Implemented in a Firewall or a Router or a Switch <br/>
- Quality of Service (QoS) <br/>
	- Setting Priorities of Different Applications <br/>
		- Prioritising Bandwidth / Traffic Rates [Application Uses] <br/>
			- Broad Description to Define the Process of Controlling Traffic Flows <br/>
	- Class of Service (CoS) <br/>
		- Configure on an OSI Layer 2 Network <br/>
			- Prioritisation Performed inside Ethernet Frame Header [``802.1Q`` Trunk] <br/>
				- Very Specific to Communication between Switches <br/>
					- Commonly performed inside of own Intranet <br/>
						- ``!=`` Common to have a Trunk Connection to ISP <br/>
	- QoS at OSI Layer 2 (Trunk) Confining [Implement DiffServ] <br/>
		- Differentiated Services (DiffServ) <br/>
			- Configure on an OSI Layer 3 Network <br/>
				- Modifying QoS Bits within the IPv4 Header <br/>
					- Bits Usually Set Outside of the Application <br/>
						- Device Recognises Application [Sets Bits inside Header] <br/>
							- Done inside Routers / Firewalls [with DiffServ capability] <br/>
						- Differentiated Services Code Points (DSCP) <br/>
							- Values Applied inside of IP header <br/>
								- Specific Field [DS or Differentiated Services Field] <br/>
	- Some Environments may take Advantage of both CoS and DiffServ <br/>
</details>

<details close>
	<summary>Network Address Translation</summary>

- IPv4 supports c. 4.29B Addresses <br/>
	- Over 20B Devices are Connected to the Internet [Estimated] <br/>
		- Number is Increasing [Need to be able to Communicate Between All] <br/>
			- Exhausted IPv4 Address Space [No More Addresses that can be Assigned] <br/>
- Private (RFC 1918) IPv4 Addresses <br/>
	- Used inside an Organisation <br/>
		- ``!=`` Routable accross Internet <br/>
		![Image: IPv4 Private Addresses](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/ipv4-private-addresses.png?raw=true) <br/>
		- Network Address Translation (NAT) <br/>
			- Network [Single Device] <br/>
				- Translate Private into something that is Public [Internet] <br/>
					- Router performs NAT [``10.10.20.50`` is Private] <br/>
					![Image: Router Performs NAT](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/router-performs-nat.png?raw=true) <br/>
						- Translates IP Address [Send Across Internet] <br/>
							- Using (Router) External IP Address [``94.1.1.1``] <br/> 
							![Image: Router Translates to Public Address](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/router-translates-to-public.png?raw=true) <br/>
					- Server Receives Request [Sends Response] <br/>
						- Destination Address is Source Address <br/>
							- Router Checks Table [Inbound on ``94.1.1.1``] <br/>
							![Image: Router Translates to Public Address](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/route-nat-to-source.png?raw=true) <br/>
								- Performs another NAT [``10.10.20.50``] <br/>
								![Image: Router Performs another NAT](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/router-performs-nat-source.png?raw=true) <br/>
			- Network [Multiple Devices] <br/>
				- NAT Overload (Source NAT) / PAT [Port Address Translation] <br/>
					- Perform NAT on Source IP Address <br/>
					![Image: NAT Overload](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/nat-overload.png?raw=true) <br/>
						- Table Keeps Track of Translations <br/>
						![Image: Route Table](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/router-nat-public-address.png?raw=true) <br/>
			- Other Type of NAT Found on Router <br/>
				- Port Forwarding <br/>
					- Outside [Access Inside Devices] <br/>
						- 24x7 Access to a Service Hosted Internally <br/>
							- Hosting [Devices have Private Addresses] <br/>
								- Web Server <br/>
								- Gaming Server <br/>
								- Security System etc <br/> 
						- External IP/Port Number Associate to an Internal IP/Port <br/>
							- Does Not have to be the Same Port Number <br/>
								- Communicate to Router from Outside [External IP Address] <br/>
									- Referred as Destination NAT or Static NAT <br/>
									- Destination Address Translated from Public IP to Private IP <br/>
									![Image: Port Forwarding](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/port-forwarding.png?raw=true) <br/>
									- Given NAT is Static ``!=`` Expire or Timeout [Available 24/7] <br/>
					- Inbound Communication <br/>
						- Internet Devices Communicate Internal Devices [Private IP] <br/>
							- Router performs NAT <br/>
								- Configured Inbound External Address [``66.20.1.14``] <br/>
									- Translate to Private Address [``192.168.3.22``] <br/>
									![Image: Port Forwarding Translation](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/port-forwarding-translation.png?raw=true) <br/> 
</details>

<details close>
	<summary>Access Control Lists</summary>

- Access Control List (ACL) is a Packet Filter <br/>
	- Allow or Deny Traffic <br/>
		- Also used for Network Address Translation (NAT) <br/>
			- Determine what IP Addresses need to be Translated <br/>
		- Quality of Service (QoS) <br/>
			- Know Type of Traffic needing Priority <br/>
	- Common Configuration on Router Interface <br/>
		- Defined on the Ingress or Egress of an Interface <br/>
			- Traffic Incoming or Outgoing or Both <br/>
	- Can Evaluate on Certain Criteria [Specific] <br/>
		- Decision to Allow or Deny [Particular Packet] <br/>
			- Examine Source IP <br/>
			- Examine Destination IP <br/>
			- Examine TCP Port Numbers <br/>
			- Examine UDP Port Numbers <br/>
			- Examine ICMP <br/>
		- IP Address Range or TCP Ports <br/>
			- Traffic Flow Matches Combination <br/>
				- Deny or Permit Traffic from Router Interface <br/>
	- Evolved Through the Years [Different Manufacturers] <br/>
		- More Options and Features Available for Traffic Filtering <br/>
- Rule Base inside Firewall can be considered an ACL <br/>
	- Allow or Disallow Traffic through the Firewall <br/>
		- Conbination of Variables [Tuple] <br/>
			- Groupings of Tuples [Specific ACL Rule]
				- Source IP <br/>
				- Destination IP <br/>
				- Port Number <br/>
				- Time of Day / Application etc <br/>
	- Firewall Logic normally Starts with the 1st Rule <br/>
		- Usually top-to-bottom <br/>
			- Match then Firewall ``!=`` Proceed Further down Rule Base <br/>
				- Can be very General or very Specific <br/>
					- Specific Rules are Usually at the Top <br/>
- Most ACLs & Firewall Rule Bases written with Implicit Deny <br/>
	- Most Firewalls include a Deny at the Bottom <br/>
		- Default Deny is Implicit <br/>
- Web Service Firewall Ruleset <br/>
	- First Rule <br/>
		- Rule Number [Tuple] <br/>
			- Remote IP [Tuple] <br/>
				- Allow All Traffic from Romote IP via Remote Port [Tuple] <br/>
					- Communicating to Local Port ``22`` via Local Port [Tuple] <br/>
						- Protocol [Tuple] <br/>
							- TCP [Port ``22`` probably SSH Traffic] <br/>
								- Action [Tuple] <br/>
									- Firewall set to Allow Traffic <br/>
									![Image: Ruleset](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/web-service-firewall-ruleset.png?raw=true) <br/>
		- No Rule Applying then Implicit Deny at Bottom <br/>
			- Not Matching Specific Rule Automatic Drop <br/>
</details>

<details close>
	<summary>Circuit Switching and Packet Switching</summary>

- Circuit Switching <br/>
	- Circuit is Established between Endpoints before Data is Sent <br/>
		- Phone Network <br/>
			- Plain Old Telephone Service (POTS) <br/>
			- Public Switched Telephone Network (PSTN) <br/>		
				- Call [Circuit Established then Talk] <br/>
		- Connection is Always There <br/> 
			- Nobody can Use the Circuit when Idle <br/>
				- Inefficient Use of Resources <br/>
			- Create Circuit between x2 Remote Sites [Advantage] <br/>
				- Not Sharing Capacity [Guaranteed] <br/>
				- Network Always Aavailable [Not Waiting] <br/>
		- T1 / T3 [E1 / E3 (Outside USA)] Network <br/>
			- Circuit Created between Two Links [Wide Area Connections] <br/>
				- Alway Available between the Two Connections <br/>
		- Integrated Services Digital Network (ISDN) Network <br/>
			- ISDN Modem calls Another ISDN Modem <br/>
				- Alway Available Until the ISDN Connection is Terminated <br/>
- Packet Switching <br/>
	- Data is Grouped into Packets [Sent across the Network] <br/>
	- Media is Usually Shared [Someone Else Can Use It when You are Not] <br/>
	- Supports Qualities of Service <br/>
		- Someone may have Higher Priority over Someone Else <br/>
			- One Connection may have More Bandwidth Allocated <br/>
				- How much Money would you like to spend? <br/>
	- Technologies <br/>
		-  Synchronous Optical Network (SONET) <br/>
			- Physical Layer Specification for Broadband Synchronous Transmission <br/>
				- Data over Long Distances of Fiber-optic Cabling [Speeds >1 Gbps] <br/>
		- Asynchronous Transfer Mode (ATM) <br/>
			- Switching Technique [Time Division Multiplexing (TDM)] <br/>
				- ATM Networks are Connection-oriented Networks <br/>
		- Digital Subscriber Line (DSL) <br/>
			- Transmit Digital Data over Telephone Lines <br/>
		- Frame Relay <br/>
			- Standardized WAN technology <br/>
				- Specifies the Physical and Data Link Layers of Telecom Channels <br/>
		- Multiprotocol Label Switching (MPLS) <br/>
			- Routing Technique <br/>
				- Traffic from One Node to the Next using Labels [``!=`` Addresses] <br/>
		- Cable Modem Internet Connection <br/>
		- Satellite <br/>
		- Wireless <br/>
</details>

<details close>
	<summary>Software Defined Networking (SDN)</summary>

- Networking Devices have x2 Functional Planes of Operation <br/>
	- Control Plane <br/>
		- Administration [ongoing Servicing] <br/>
	- Data Plane <br/>
		- Forwarding Data <br/>
- Key Features <br/>
	- Directly Programmable <br/>
		- Data Plane Separate Process to the Control Plane <br/>
			- Make Configuration Changes <br/>
			- View Log Information <br/>
	- Agile <br/>
		- Changes made Dynamically <br/>
			- Part of the Network get Busy [Dynamically Changed] <br/>
	- Centrally Managed [Central Console] <br/>
		- No Need to Log into Multiple Places to Manage Network <br/>
			- Global View [Single Pane of Glass] <br/>
				- Single Screen [Control Entire Network] <br/>
	- Orchestration [No Human Intervention] <br/>
		- Programmatically Configured <br/>
			- Automatic Network Operation <br/>
				- Section of Network Congested [Resources Deployed Automatically] <br/>
	- Open Standards [Vendor Neutral] <br/>
		- Standard Interface to the Network <br/>
- SDN Functionality Enabled due to Virtualised Portions of Infrastructure <br/>
	- Servers / Routers / Firewalls / Switches <br/>
		- Network with Physical Switch [Physical World] <br/>
			- Servers built to Host Virtual Environments [Physical World] <br/>
				- Top of Servers (Web Server / DB Server / Test Server) [Virtual World] <br/>
					- Challenge [Separate out Devices into there own VLANS] <br/>
						- Test Server Separate VLAN to Web Server / DB Server <br/>
						![Image: SDN Physical & Virtual](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/sdn-physical-virtual.png?raw=true) <br/>
					- Challenge [Virtual Devices moving Anywhere in Network] <br/>
						- May Need More Network Capacity [or Less Capacity] <br/>
							- Services Moves / Allows Access along with Server <br/>
	- Distributed Switching	<br/>
		- Virtualised Networking <br/>
			- Group Individual Services into own VLAN] <br/>
				- Removing the Physical Segmentation <br/>
					- Virtual Network Distributed across all Physical Platforms <br/>
					- When a VM Moves then Network ``!=`` Change <br/>
						- Servers will always Connect to the Right VLAN <br/>
				- Physical Switch [Physical World] <br/>
					- Physical Virtualisation Platforms (Host 1 / 2 / 3) [Physical World] <br/>
						- Each running Virtual Servers [Virutual World] <br/>
							- Web Server <br/>
							- DB Server <br/>
							- Test Server <br/>
						- Distributed Switch <br/>
							- Grouping Different Resources into own VLAN	<br/>		![Image: Distibuted Switch](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/distibuted-switch.png?raw=true) <br/>
</details>

##### ``Network Addressing``

<details close>
	<summary>Binary Math</summary>

- [Binary Math](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-binary-math.ipynb#networkConceptsBinaryMath) <br/>
    - [Binary to Decimal Conversion](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-binary-math.ipynb#networkConceptsBinaryMathBinarytoDecimal) <br/>
    - [Decimal to Binary Conversion](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-binary-math.ipynb#networkConceptsBinaryMathDecimaltoBinary) <br/>
- [More Bits then More Addresses](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-binary-math.ipynb#networkConceptsBinaryMathMoreBitsthenMoreAddresses) <br/>
    - [Powers Of Two](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-binary-math.ipynb#networkConceptsBinaryMathPowersOfTwo)
</details>

<details close>
	<summary>IPv4 Addresses</summary>

- [Configuring Layer 3 Devices](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsConfiguringLayer3Devices) <br/>
    - [IP Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsIPAddress) <br/>
    - [Subnet Mask](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsSubnetMask) <br/>
    - [Default Gateway - Router IP Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsDefaultGateway) <br/>
- [Special IPv4 Addresses](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsSpecialIPv4Addresses) <br/>
    - [Loopback Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsSpecialIPv4AddressesLoopbackAddress) <br/>
        - [[``127.0.0.1``,``127.255.255.254``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsSpecialIPv4AddressesLoopbackAddressRange) <br/>
    - [Reserved Addresses](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsSpecialIPv4AddressesReservedAddress) <br/>
        - [[``240.0.0.1``,``255.255.255.254``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsSpecialIPv4AddressesReservedAddressRange) <br/>
- [Virtual IP Address - VIP](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-addresses.ipynb#networkConceptsVirtualIPAddressVIP)
</details>

<details close>
	<summary>Classful Subnetting</summary>

- [Early IP Protocol Subnet Masks](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasks) <br/>
    - [Class A Subnet Mask](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasksClassA) <br/>
        - [[``255.0.0.0``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasksClassA) <br/>
    - [Class B Subnet Mask](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasksClassB) <br/>
        - [[``255.255.0.0``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasksClassB) <br/>
    - [Class C Subnet Mask](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasksClassC) <br/>
        - [[``255.255.255.0``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#networkConceptsEarlyIPProtocolSubnetMasksClassC) <br/>
- [Class-based Subnet Masks](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassBasedSubnetMasks) <br/>
    - [Subnet Classes Associated IP Addresses](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#SubnetClasses) <br/>
        - [Class A IP Addresses 1st Octet](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassAIPAddresses) <br/>
            - [[``1``,``126``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassAIPAddresses) <br/>
                - [(``0``,``127``)](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassAIPAddresses) <br/>
        - [Class B IP Addresses 1st Octet](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassBIPAddresses) <br/>
            - [[``128``,``191``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassBIPAddresses) <br/>
                - [(``127``,``192``)](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassBIPAddresses) <br/>
        - [Class C IP Addresses 1st Octet](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassCIPAddresses) <br/>
            - [[``192``,``223``]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassCIPAddresses) <br/>
                - [(``191``,``224``)](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassBIPAddresses) <br/>
        - [Class D Multicast and Class E Reserved](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ClassOtherIPAddresses) <br/>
    - [IP Address Associated Class](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
        - [``17.22.90.7``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
            - [Class A](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
        - [``220.10.77.40``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
            - [Class C](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
        - [``165.245.0.1``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
            - [Class B](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
        - [``128.90.10.2``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
            - [Class B](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
        - [``191.77.24.250``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
            - [Class B](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
        - [``192.1.12.5``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
            - [Class C](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#ipAddressAssociatedClass) <br/>
- [Subnet Construction](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetConstruction) <br/>
    - [Network Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetConstructionNetworkAddress) <br/>
    - [Host Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetConstructionHostAddress) <br/>
    - [Network Broadcast Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetConstructionNetworkBroadcastAddress) <br/>
- [Subnet Calculations](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculations) <br/>
    - [``10.74.222.11``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculations) <br/>
        - [Class A](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculations) <br/>
            - [Default Subnet Mask](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculations) <br/>
                - [``255.0.0.0``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculations) <br/>
        - [Network Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsNetworkAddress) <br/>
            - [``10.0.0.0``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsNetworkAddress) <br/>        
        - [``Host Address``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsFirstHostAddress) ``[0]`` <br/>
            - [``10.0.0.1``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsFirstHostAddress) <br/>        
        - [Broadcast Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsBroadcastAddress) <br/>
            - [``10.255.255.255``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsBroadcastAddress) <br/>
        - [``Host Address``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsLastHostAddress) ``[len(ADDR)-1]`` <br/>
            - [``10.255.255.254``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#subnetCalculationsLastHostAddress) <br/>
- [Classful Subnetting](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-classful-subnetting.ipynb#classfulSubnetting)
</details>

<details close>
	<summary>IPv4 Subnet Masks</summary>

- [The Subnet Masks](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#theSubnetMask) <br/>
    - < [Classless Inner Domain Routing - CIDR](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#classlessInnerDomainRoutingCIDR) | [Prefix Notation](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#classlessInnerDomainRoutingCIDR) | [Slash Notation](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#classlessInnerDomainRoutingCIDR) > <br/>
        - [Binary to CIDR-block Notation](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
            - [``11111111.11111111.00000000.00000000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                - [``/16``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                    - [``Network 16 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                    - [``Host 16 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
            - [``11111111.11111111.11111111.11000000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                - [``/26``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                    - [``Network 26 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                    - [``Host 6 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/> 
            - [``11111111.11110000.00000000.00000000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                - [``/12``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                    - [``Network 12 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>
                    - [``Host 20 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblocknotation) <br/>                     
    - [Binary to Decimal](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
        - [Chart](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``00000000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``0``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``10000000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``128``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11000000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``192``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11100000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``224``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11110000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``240``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11111000``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``248``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11111100``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``252``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11111110``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``254``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
            - [``11111111``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
                - [``255``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoDecimal) <br/>
        - [Binary to CIDR-block Notation](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#binarytoCIDRblockNotation) <br/>          
- [CIDR Notation to Binary](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv4-subnet-masks.ipynb#cIDRNotationtoBinary)
</details>

<details close>
    <summary>IPv6 Subnet Masks</summary>
    
- [Internet Assign Numbers Authority - IANA](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#internetAssignNumbersAuthorityIANA) <br/>
    - [Regional Internet Registries - RIRs](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#regionalInternetRegistriesRIRs) <br/>
        - [Internet Service Provider - ISP](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#internetServiceProviderISP) <br/>
            - [Customer](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#internetServiceProviderISPCustomer) <br/>
- [Subnetting the IPv6 Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#subnettingtheIPv6Address) <br/>
    - [Global Routing Prefix](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#subnettingtheIPv6AddressGlobalRoutingPrefix) | [``48 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#subnettingtheIPv6AddressGlobalRoutingPrefix) <br/>
        - [Assigning Subnet](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#globalRoutingPrefixAssigningSubnets) | [``16 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#subnettingtheIPv6AddressGlobalRoutingPrefix) <br/>
            - [IPv6 Address Network](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#globalRoutingPrefixAssigningSubnetsNetworkAddress) | [``64 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#globalRoutingPrefixAssigningSubnetsNetworkAddress) <br/>
            - [IPv6 Address Host](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#globalRoutingPrefixAssigningSubnetsHost) | [``64 bits``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#globalRoutingPrefixAssigningSubnetsHost) <br/>
    - [Subnet Mask](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-ipv6-subnet-masks.ipynb#subnettingtheIPv6AddressSubnetAddress)
</details>

<details close>
    <summary>Calculating IPv4 Subnets and Hosts</summary>

- [Subnet the Network](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#subnettheNetwork) <br/>
- [Variable Length Subnet Masks - VLSM](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#variableLengthSubnetMasksVLSM) <br/>
    - [Classless Addressing](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#variableLengthSubnetMasksVLSMDefineSubnet) <br/>
        - [``10.0.0.0``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#variableLengthSubnetMasksVLSMDefineSubnet) <br/>
            - [``255.0.0.0/8``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#variableLengthSubnetMasksVLSMDefineSubnet) <br/>
        - [Borrowing Subnet Bits](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#variableLengthSubnetMasksVLSMDefineSubnetBorrow) ``16`` <br/>
            - [``255.255.255.0/24``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#variableLengthSubnetMasksVLSMDefineSubnetBorrow) <br/>
- [Calculating Subnets and Hosts](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
    - [``10.1.1.0/24``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
        - [Possible Networks](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHostsTotalNetworks) <br/>
            - [``65,536``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHostsTotalNetworks) <br/>
        - [Possible Hosts](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHostsTotalHosts) <br/>
            - [``254``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHostsTotalHosts) <br/>
    - [``192.168.11.0/26``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
        - [Possible Networks](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
            - [``4``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
        - [Possible Hosts](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
            - [``62``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
    - [``172.16.55.0/21``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
        - [Possible Networks](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
            - [``32``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
        - [Possible Hosts](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts) <br/>
            - [``2046``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-calculating-ipv4-subnets-and-hosts.ipynb#calculatingSubnetsandHosts)
</details>

<details close>
    <summary>Seven Second Subnetting</summary>

- [Seven Second Subnetting](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-seven-second-subnetting.ipynb) 
</details>

<details close>
    <summary>Assigning IPv4 Addresses</summary>

- [Assigning IPv4 Addresses](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#networkConceptsAssigningIPv4Addresses) <br/>
    - [Bootstrap Protocol - BOOTP](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#networkConceptsAssigningIPv4AddressesBOOTP) <br/>
        - [Dynamic Host Configuration Protocol - DHCP](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCP) <br/>
            - [DHCP Pool](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPDHCPPool) <br/>
        - [Turning Dynamic into Static](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPTurningDynamicintoStatic) <br/>
            - [Manual Configuration](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPTurningDynamicintoStaticManualConfiguration) <br/>
                - [Disable DHCP](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPTurningDynamicintoStaticManualConfiguration) <br/>
            - [IP Reservation](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPTurningDynamicintoStaticIPReservation) <br/>
                - [Enable DHCP](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPTurningDynamicintoStaticIPReservation) <br/>                
                    - [Server MAC Associate IP Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#dynamicHostConfigurationProtocolDHCPTurningDynamicintoStaticIPReservation) <br/>
    - [Automatic Private IP Addressing - APIPA](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPA) <br/>
        - [Link-Local Address](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPA) <br/>
            - [Reserved](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPAReservedAddresses) <br/>          
                - [\[``169.254.0.1,169.254.255.254``\]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPAReservedAddresses) <br/>   
            - [Functional](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPAFunctionalAddresses) <br/>                          
                - [\[``169.254.1.0,169.254.254.255``\]](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPAFunctionalAddresses) <br/>
        - [Configuration](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPAConfiguration) <br/>
            - [``169.254``](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv4-addresses.ipynb#automaticPrivateIPAddressingAPIPAConfiguration)        
</details>

<details close>
    <summary>Assigning IPv6 Addresses</summary>
    
- [DHCPv6](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv6-addresses.ipynb#networkConceptsAssigningIPv6Addresses) <br/>
    - Stateful Dynamic Host Configuration Protocol Version 6 (DHCPv6) <br/>
        - IPv6 Interface Configuration [``!=`` Broadcasts] <br/>
            - Link-Local ADDR [Automatic] <br/>
                - ``fE80`` <br/>
            - Multicast <br/>
                - Client ``udp/546`` <br/>
                - Server ``udp/547`` <br/>
        - DHCPv6 Steps <br/>
            - Client ``fe80:aabb:ccff:fedd:eeff`` <br/>                           
                - i. DHCPv6 Solicit Message <br/>
                    - Multicast ADDR <br/>
                        - ``udp/547`` [Server] <br/>
                            - ``[ff02::1:2]:547`` <br/>
                                - DHCP Server [Seek] <br/>
            - Server ``fe80::0011:22ff:fe33:5566`` <br/>
                - ii. DHCPv6 Advertise Message <br/>
                    - ``udp/546`` [Client] <br/> 
                        - Associated IP ADDR <br/>
            - Client <br/>
                - List All Adverticement [DHCP Servers] <br/>
                    - iii. DHCPv6 Request Message <br/>
                        - Multicast ADDR <br/>
                            - ``udp/547`` [Server] <br/>
                                - ``[ff02::1:2]:547`` <br/>
                                    - Picks x1 <br/>
            - Server <br/>
                - iv. DHCPv6 Reply Message <br/>
                    - ``udp/546`` [Client] <br/>
                        - Client Configures IP ADDR Assigned <br/>
- [IPv6 Prefix - Modified MAC](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv6-addresses.ipynb#networkConceptsAssigningIPv6AddressesOther) <br/>
    - Static IP [ADDR Never Changes] <br/>
        - Media Access Control - MAC [ADDR Never Changes] <br/>
            - Physical Address [Network Interface Card - Ethernet Network] <br/>
                - ``EUI-48`` ADDR [Extended Unique Identifier] <br/>
                    - ``48-bit`` [MAC ADDR] <br/>
                        - Organizationally Unique Identifer (OUI) <br/>
                            - Manufacturer <br/>
                                - ``24-bit`` <br/>
                        - Network Interface Controller-Specific <br/>
                            - Serial Number <br/>
                                - ``24-bit`` <br/>
    - Modify MAC ADDR [Create Static IPv6 ADDR] <br/>
        - Extended Unique Identifier - EUI ADDR <br/>
            - ``64-bit`` <br/>
                - MAC ADDR <br/>
                    - ``48-bit`` [Create ``64-bit`` EUI ADDR] <br/>
        - Converting EUI-48 TO EUI-64 <br/>
            - Modifying MAC <br/>
                - Split ``24-bit`` <br/>
                    - Insert Middle ``16-bit`` <br/>
                        - ``FFFE`` <br/>
                - Change Original MAC ADDR ``8c2d:aa`` <br/>
                    - Modify Seventh Bit <br/>
                        - Burned-in ADDR - BIA <br/>
                            - Locally Administered ADDR ``U/L`` [Universal / Local] <br/>
                                - ``0`` to ``1`` [``8e2d:aa``] <br/>
    - Build IPv6 ADDR <br/> 
        - Routers [Local Subnet] <br/>
            - Send Neighbour Discovery Protocol - NDP <br/>
                - IPv6 Subnet Prefix ``2600:dddd:1111:0001`` <br/>
                    - ``64-bit`` <br/>
        - EUI-64 ADDR [Remaining ``64-bit``] <br/>
            - ``3-byte`` MAC <br/>
                - Modified MAC ADDR ``8e2d:aa`` <br/>
            - ``2-byte`` <br/>
                - ``FFFE`` <br/>
            - ``3-byte`` MAC [Unchanged Remaining] <br/>
- [Converting EUI-48 TO EUI-64 - Flipping the 7th bit](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/networking-addressing/nkp-assigning-ipv6-addresses.ipynb#ConvertingEUI48TOEUI64Flippingthe7thbit)
</details>           

##### ``Network Topologies``

<details close>
    <summary>Network Topologies</summary>

- Map [Diagram] <br/>
    - [Physical Network](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-network-topologies.ipynb#physicalNetworkMap) <br/>
    - [Logical Network](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-network-topologies.ipynb#logicalNetworkMap) <br/>
- [Topologies](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-network-topologies.ipynb#networkConceptsNetworkTopologies) <br/>
    - Star (Switch Networks) <br/>
    - Ring (Metropolitan Area Network and Wide Area Network) <br/>
        - Dual [Fault tolerance] <br/>
    - Mesh (Wide Area Networks) <br/>
        - Additional Fault Tolerance [Redundant] <br/>
        - Balance Load between Multiple Links <br/>
    - Bus (Controller Area Network - Can) <br/>
        - Single Coax Cable <br/>
            - Automobile <br/>
    - Wireless ``802.11`` <br/>
        - Infrastructure <br/>
            - Access Point <br/>
        - Ad hoc [No Access Point in the Middle] <br/>
            - End-stations Configured [Frequency] <br/>
        - Mesh (Internet of Things) <br/>
            - Self Form [Mesh Cloud] <br/>
                - Self Heal
</details>

<details close>
    <summary>Common Network Types</summary>

- [Common Network Types](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-common-network-types.ipynb#networkConceptsCommonNetworkTypes) <br/>
	- Local Area Network - LAN <br/>
        - Ethernet <br/>
        - Wireless ``802.11`` <br/>
	- Wireless LAN - WLAN [Exclusive] <br/>
        - ``802.11`` <br/>
            - Access Points [Expand] <br/>
	- Metropolitan Area Network - MAN <br/>
        - City Network [Government Ownership] <br/>
            - ``>`` LAN [``<`` WAN] <br/>
	- Wide Area Network - WAN <br/>
        - ``>`` MAN [Connects LANs across a Distance] <br/>        
            - Point-to-point Serial Connection [Technology] <br/> 
            - Multiprotocol Label Switching (MPLS) Connection [Technology] <br/> 
            - Satellite Connection [Technology] <br/>
                - Non-terrestial Links <br/> 
	- Campus Area Network - CAN <br/>
        - Building in Office Block [College Campus] <br/>
            - Limited Geographical Area <br/> 
                - Fiber Connection [Technology] <br/> 
                    - No 3rd Party Provider [Own Fiber in Ground] <br/> 
                - High-speed Ethernet [Technology] <br/> 
- [Connect Hard Drive](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-common-network-types.ipynb#connectHardDrive) <br/>
    - Network Attached Storage - NAS <br/>
        - Remote Shared Storage <br/>
            - File-level Access <br/>
                - Change Part of File [Replace Entire File] <br/>
    - Storage Area Network - SAN <br/>
        - Extension of Computer [Look / Feel Local Storage Device] <br/>
            - Block-level Access [Efficient Reading & Writing] <br/>
                - Change Part of File [Blocks Changed Only] <br/>  
                    - ``!=`` Entire File <br/>
    - Requires a lot of Bandwidth (Reading / Writing) [NAS & SAN] <br/>
        - Connect via High-speed Network Topologies <br/>      
- [Personal Area Network - PAN](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-common-network-types.ipynb#personalAreaNetworkPAN) <br/>
    - Private Network <br/>
        - Bluetooth [Device Connection] <br/>
        - Infrared [Device Connection] <br/>
        - Near-Field Communication - NFC [Device Connection] 
</details>

<details close>
    <summary>Internet of Things Topologies</summary>

- [Internet of Things Topologies](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-internet-of-things-topologies.ipynb#networkConceptsInternetofThingsTopologies) <br/>
	- Z-wave [IoT Technology Category] <br/>
        - Home Automation Networking <br/>
            - Wireless Mesh Network <br/>
                - Nodes Hop through Other Nodes <br/>
		- Frequency ``900 MHz`` [Communication] <br/>
            - Industrial Scientific and Medical (ISN) Band <br/>
                - ``!=`` License to use Frequencies <br/>
                - ``!=`` Conflicts with other ``802.11`` Devices <br/>
	- ANT/ANT+ [Wireless Network Protocols] <br/>
		- Frequencey ``2.4 GHz`` [Communication] <br/>
            - Industrial Scientific and Medical (ISN) Band <br/>
                - Ultra-Low-Power Protocol <br/>
                    - ``!=`` (``802.11`` ``||`` Bluetooth) <br/>
                        - Separate Wireless Service <br/>
            - Denial of Service [Spectrum can be Jammed] <br/>
            - Optional Encryption [``!=`` Required for Communication] <br/>
	- Bluetooth <br/>
        - Personal Area Network - PAN <br/>
	- Near Field Communication - NFC [Mobile Phone] <br/>
        - Two-way Wireless Communication <br/>
            - Payment Systems <br/>
                - Credits Cards <br/>
                - Online Wallets <br/>
            - With Other Network Types [Bootstrap other Wireless] <br/>
                - Bluetooth Pairing <br/>
            - Access Token [Identity Card] <br/>
                - Short Range with Encryption Support <br/>            
                    - Electronic Locks <br/>
	- Infrared - IR <br/>
        - Integrated on Smartphones & Tablets & Smartwatches <br/>
            - ``!=`` File Transfers ``||`` Printing [Historic] <br/>
                - Entainment Centre via Mobile Device [Today] <br/>
	- Radio-Frequency Identification - RFID <br/>
		- Radio Energy [Transmitted to Tag] <br/>
            - RF Powers Tag <br/>
                - Tag Transmits Back ID [Bidirectional Wireless Communication] <br/>
                   - Some Tag Formats can be Active / Powered <br/>
        - Access Badges <br/>
        - Inventory / Assembly Line Tracking <br/>
        - Pet / Animal Identificaiton <br/>
        - Anything Needing Tracking <br/>
	- IEEE ``802.11`` [Wireless Networks] <br/>
        - IEEE LAN / MAN <br/>
            - WiFi Trademark [Compatibility]       
</details>

##### ``Wireless Technologies``

<details close>
    <summary>Wireless Standards</summary>

- [``802.11`` Wireless Standards](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-internet-of-things-topologies.ipynb#networkConcepts80211WirelessStandards) <br/>
	- ``802.11a`` [October 1999 - Not Commonly Seen Today] <br/>
		- ``5 GHz`` Frequency Range [Smaller Range Than ``802.11b``] <br/>
            - Absorbed by Objects [High Frequency] <br/>
                - Calculate Third Range of ``802.11b`` or ``802.11g`` <br/>
        - ``54 Mbit/s`` Throughput <br/>
	- ``802.11b`` [Released Simultaneously with ``801.11a`` Standard] <br/>
		- ``2.4 GHz`` Frequency Range [Better Range Than ``802.11b``] <br/>
            - Less Absortion Problems <br/>
                - Bounce off of Objects <br/>
            - Communication Conflicts [Other Devices @ ``2.4 GHz`` Frequency] <br/>
                - Baby Monitors [Operate @ ``2.4 GHz``] <br/>
                - Cordless Phones [Operate @ ``2.4 GHz``] <br/>
                - Microware Ovens [Operate @ ``2.4 GHz``] <br/>
                - Bluetooth Communications [Operate @ ``2.4 GHz``] <br/>
        - ``11 Mbits/s`` Throughput [Maximum] <br/>
	- ``802.11g`` [June 2003] <br/>
        - Upgrade to ``802.11b`` <br/>
            - Backwards Compatible with ``802.11b`` <br/>
                - ``802.11g`` Access Point can Accommodate ``802.11b`` Clients <br/>
		- ``2.4 GHz`` Frequency Range [Issues as ``802.11b``] <br/>
            - Communication Conflicts [Other Devices @ ``2.4 GHz`` Frequency] <br/>
        - ``54 Mbit/s`` Throughput [Similar to ``802.11a``] <br/>        
	- ``802.11n`` [October 2009] <br/>
        - Upgrade to ``802.11g`` & ``802.11b`` & ``802.11a`` <br/>
		- ``5 GHz`` and / or ``2.4 GHz`` Frequency Range <br/>
            - Channel Bandwidths of ``40 MHz`` [``>`` Previous ``802.11`` Versions] <br/>
        - ``600 Mbit/s`` Throughput <br/>
            - Via ``40 MHz`` Channel Width [``4`` Antennas] <br/>
                - Sending Multiple Streams of Data Simultaneously <br/>
		- Multiple Input Multiple Output - MIMO [1st Version] <br/>
            - Send Multiple Streams over Same Frequency <br/>
                - Multiple Antennas / Radios [Send the Data] <br/>
	- ``802.11ac`` [January 2014] <br/>
        - Significant Improvement Over ``802.11n`` <br/>
        - ``5 GHz`` Frequency Range [Exclusively] <br/>
            - Some ``802.11ac`` Routers Communicate over ``5 GHz`` & ``2.4 GHz`` <br/>
                - ``2.4 GHz`` Communication via ``802.11n`` <br/>
            - Channel Bandwidths of ``160 MHz`` [``5 GHz`` Less Crowded & More Frequencies] <br/>
            - Channel Bonding [Creating Larger Channel Bandwidths] <br/>
            - Denser Signalling Modulation [Faster Data Transfers] <br/>
        - Multi-User Mulitiple Input Multiple Output (MU-MIMO) <br/>
            - Eight MU-MIMO <br/>
                - Twice as many Streams as ``802.11n`` <br/>
                    - ``7 GBits/s`` Throughput [Theory] <br/>
    ![Summary](https://github.com/SeanOhAileasa/SeanOhAileasa/blob/master/rc/nkp/802-11-networking.png?raw=true)
</details>

<details close>
    <summary>Cellular Network Standards</summary>
    
- [Cellular Network Standards](https://nbviewer.org/github/SeanOhAileasa/nkp-network-concepts/blob/main/rc/network-topologies/nkp-cellular-network-standards.ipynb#networkConceptsCellularNetworkStandards) <br/>
    - 2G Networks <br/>
        - Circuit Switching <br/>
            - i. Global System for Mobile Communications (GSM) <br/>
                - Time Division Multiple Access (TDMA) Multiplexing <br/>
            - ii. Code Division Multiple Access (CDMA) <br/>
    - 4G Networks <br/>
        - Long Term Evolution (LTE) <br/>
            - GSM and EDGE (Enhanced Data Rates for GSM Evolution) <br/>
            - Download Data Rates up to ``150 Mbits/s``  <br/> 
        - LTE Advanced <br/> 
            - Download Data Rates up to ``300 Mbits/s``
</details>

## Credits

J. "Professor" Messer, "CompTIA Network+ (N10-007) Course Notes," [professormesser.com](https://web.archive.org/web/20220404153917/https://www.professormesser.com/network-plus/n10-007/n10-007-training-course/), March 2019.

## END