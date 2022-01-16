# Introduction to LAN

## Introducing LAN Topologies
- In a ring network, a device will only send received data from another device if it does not have data to send.
	- Will send it's own data first bfore sending data from another device.
	
> **Switch** - dedicated devices within a network.
>	- Designed to aggregate multiple other devices (e.g., computers or printers) or other networking-capable devices using ethernet.
>	- Plug devices into the switch's ports.
>	- More efficient than hubs/repeaters.
>		- Keep track of what device is connected to which port.
>		-  Instead of just repeating that packet to every port like a hub would do, sends to intended target reducing network traffic.
>- Switches and routers can be connected to one another.
> - Increases redundancy (reliability) of a network by adding multiple paths for the data to take.
>		- If one path goes down, another can be taken.
>		- May reduce overall performance as packets have to take longer to travel.

## The ARP Protocol
- Devices have two identifiers - MAC address and IP address.
- ARP protocol - responsible for allowing devices to identify themselves on a network.
- ==Address Resolution Protocol==
- Allows a device to associate its MAC address with an IP address on the network.
- Each device on a network - keep log of the MAC addresses associated with other devices.
- Devices with to communicate with each other - they send a broadcast to the entire network searching for a specific device.
	- Can use the ARP protocol to find the MAC address (and the physical identifier) of a device for communication.

### How Does It Work?
- Each device on network - ledger to store information - ==cache==.
	- Cache stores identifiers of other devices on the network.
- Map these two identifiers together (IP addresses and MAC addresses) - ARP protocol sends two types of messages.
	- ARP Request
	- ARP Reply
- ARP request sent - message is broadcasted to every other device found on a network by the device.
	- Asks whether or not the device's MAC address matches the requested IP address.
	- If device does have the requested IP address - ARP reply is returned.
	- Initital device - remembers this and stores it within it's cache (ARP entry).

## Dynamic Host Configuration Protocol

IP addresses either assigned:
- manually - entering them physically into a device
- automatically - (most commonly) by using a DHCP server

When device connects to a network - if it has not already been manually assigned an IP address - sends out a request (==DHCP Discover==) to see if any DHCP servers are on the network.

DHCP server replies back with an IP address the device could use (==DHCP offer==).

Device then sends reply confirming it wants to use the offered IP Address (==DHCP Request==).

DHCP server sends a reply acknowledging that this has been completed and the device can start using that IP address (==DHCP ACK==).

