Part 3: Pwning Beacon Frames
	-WLAN packets
		-LAN: onyl a few variations: Ethernet (layer 2), IP (layer 3), TCP/UDP (layer 4)
		-WLAN
			-header
			-types: management, control & data
	-SSID: network name for discovery
	-AP broadcast "Beacon Frames"
		-In wireshark, protocol 802.11
			-"IEEE 802.11 wireless LAN management frame
				-"Fixed parameters"
					-Capabilities informations tells that the transmitter is a AP
				-"Tagged parameters"
					-SSID parameter set to get SSID
					-supported rates to get bandwidth
					-DS current channel to get channel
					-Tag vendor specific to get encryption type (ex: WPA)
				-Plain text so you can inject arbitrary beacon frames (raw sockets)
					-outil MDK (murder that kill :|)
						-beacon flood (create "fake" AP)
						# mdk3 mon0 b -n $SSID
