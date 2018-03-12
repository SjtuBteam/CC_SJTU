# Network configurations types

In this present files we are going to present, explain some characteristics and limitation of four types of mainly used network configuration, Bridge networking, Nat Networking, Host Only configuration and internal configuration. 


## Bridged Networking

***B**ridged networking* connects a virtual machine to a network using the host computer's Ethernet adapter. Bridged networking connects a virtual machine to a network by using the network adapter on the host system. 


![enter image desdcription here](https://pubs.vmware.com/workstation-9/topic/com.vmware.ws.using.doc/GUID-8AB8E6E2-E16F-4E60-8421-669C96E6BF38-high.png)
*Figure A, Bridged Network Diagram*

***T**he advantage* of bridged networking is principally because of his simple configuration modes. Bridges are simple to use. By connecting a virtual machine to a network adapter on the host system, it is often **the easiest way** to give the virtual machine access to the network. 

***T**he limitation* of a network bridge is by not incurring any communication between network path and the physical hosts of the data.  Bridging does not acquire any address placement related to the physical address of the connected terminals. Thus a data packet is sent to every address. This is a not efficient **bungling way** of transporting data. 



## Nat Networking

***N**AT networking* gives a virtual machine access to network resources by using the host computer's IP address.
With NAT networking a virtual machine does not have its own IP address on the external network. Instead, a separate private network is set up on the host system. In the default configuration, a virtual machine gets an address on this private network from the virtual DHCP server. The virtual machine and the host system share a single network identity that is not visible on the external network.

![enter image description here](https://www.vmware.com/support/ws55/doc/img/nat_1_t.png)
*Figure B, NAT Network Diagram*

***T**he advantage* of NAT Networking can be useful when the number of IP addresses is limited or the host system is connected to the network through a non-Ethernet adapter.

***T**he limitation* of a NAT Network  is it's performance loss. Indeed, because NAT requires that every packet sent to and received from a virtual machine must be in the NAT network, an unavoidable performance penalty occurs.
Another limitation is the NAT does not usually allow connections to be initiated from outside the network, although you can manually configure the NAT device to set up server connections. The practical result is that some TCP and UDP protocols that require a connection be initiated from the server machine do not work automatically and some might not work at all.

## Host-Only Networking


Host-only networking creates a network that is completely contained within the host computer. Indeed, it provides a network connection between the virtual machine and the host system by using a virtual network adapter that is visible on the host operating system.



![enter image description here](https://pubs.vmware.com/workstation-9/topic/com.vmware.ws.using.doc/GUID-B8B0D851-3DF2-4999-AE86-9059AE017A9C-high.png)
*Figure C, Host- Only Network Diagram*

***T**he advantage* of Host-Only Networking is mainly his ability to create a private network on the host computer.  

***T**he limitation* of a Host-Only Network is by assigning one IP to the Virtual machine, this one will be only accessible by the box VM is running on. No other computers can access it, and since it is Host-Only it is impossible to have access to other outside network.



## Internal Networking

This is useful when testing an application, or when you are required to have two virtual machines communicating with one another through a private network without interfering with the production and any other network traffic.



# References

 1. https://www.vmware.com/support/ws55/doc/ws_net_configurations_nat.html
 2. https://www.vmware.com/support/ws4/doc/network_bridged_ws.html
 3. https://www.vmware.com/support/ws55/doc/ws_net_configurations_hostonly.html
 4. https://kb.vmware.com/s/article/2043160




