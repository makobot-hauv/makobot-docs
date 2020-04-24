# Topside Computer Configuration


TODO 

## Set up Networking on Topside Computer

These instructions assume the topside computer is running Ubuntu Linux 18.04 and ROS.

1. On the topside computer we'll use NetworkManager for convenience. Create a new connection in NetworkManager and use the "Manual" IPv4 configuration. Assign the static IP address `192.168.2.1` and the netmask `255.255.255.0`, and leave the gateway blank.

2. Find the hostname of your topside computer by running `hostname` at the command prompt.

3. Edit the `/etc/hosts` file and add the following lines:

```
192.168.2.1     <your hostname>
192.168.2.2     makobot-pi
192.168.2.13    fitlet2-1
192.168.2.169   jetson-tx2
```
