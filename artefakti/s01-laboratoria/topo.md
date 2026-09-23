Gateway:
	Adapter 1: NAT Internet access
	Adapter 2: LAN1- 192.168.1.1/24
	Adapter 3: LAN2- 192.168.2.1/24
	IP Forwarding: Enabled

Server:
	Adapter 1: LAN1- 192.168.1.2/24
	Default Gateway:  192.168.1.1


server ---LAN1 192.168.1.0/24--- gateway -----NAT
								 	|
						   LAN2 192.168.2.0/24
									|
