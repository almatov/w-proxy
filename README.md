# w-proxy utility

This is a Python written utility that establishes transparent proxy for ports 80, 443. The program uses Linux iptables.

The proxy transparently spoofs client IP address to the address of the host where program has been ran. One purpose of this program is the remote access via single board computers (like Raspberry Pi etc.) to web based configuration interfaces of any equipment. But the program can be used as usual web proxy to escape restrictions of the client or web server networks. Just browse name or IP address of the proxy host.

The utility was tested under the Armbian Linux. But it should work under any other Linux system.

## How to install

Software requirements:

    netifaces       (apt install python3-netifaces)

Run this

    sudo cp w-proxy /usr/local/bin

## How to use

Proxy to the possible gateway address of the interface eth0

	sudo w-proxy

Proxy to the specified web server IP address

	sudo w-proxy <IP>

Print help message

	w-proxy -h

Some web servers checks hostname in the HTTP request, i.e. TP–Link routers. To access these web servers you should add record to the client's /etc/hosts then browse required hostname

	<w-proxy host IP>	tplinkwifi.net
