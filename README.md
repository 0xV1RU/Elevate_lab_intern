# Elevate_lab_intern
1.finding local IP range

	Commmand : ifconfig , ip a 
	Output : eth0: flags= 4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        		inet 192.168.228.129  netmask 255.255.255.0  broadcast 192.168.228.255
		        inet6 fe80::20c:29ff:fe12:e534  prefixlen 64  scopeid 0x20<link>
		        ether 00:0c:29:12:e5:34  txqueuelen 1000  (Ethernet)
	        	RX packets 76  bytes 5483 (5.3 KiB)
		        RX errors 0  dropped 0  overruns 0  frame 0
		        TX packets 46  bytes 5718 (5.5 KiB)
	        	TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
		        device interrupt 19  base 0x2000  

		lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
		        inet 127.0.0.1  netmask 255.0.0.0
		        inet6 ::1  prefixlen 128  scopeid 0x10<host>
		        loop  txqueuelen 1000  (Local Loopback)
		        RX packets 8  bytes 480 (480.0 B)
		        RX errors 0  dropped 0  overruns 0  frame 0
		        TX packets 8  bytes 480 (480.0 B)
		        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
