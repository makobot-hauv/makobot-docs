# Networking

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

## Configure IP addresses for GigE cameras

todo

## Set up Networking on fitlet2

todo

## Set up Networking on Raspberry Pi

1. Edit `/etc/hosts` file and add the same lines as during the topside configuration.




## Set up Networking on Jetson TX2

todo

## Set up SSH Keys

As per the ROS issue described [here](https://answers.ros.org/question/244060/roslaunch-ssh-known_host-errors-cannot-launch-remote-nodes/), we have to set up SSH keys so that roslaunch can correctly SSH into the different machines. Do this step on the topside computer as that is where we will be launching the ROS processes from.

1. Generate the RSA key pair as usual:

`ssh-keygen -t rsa`

Save the file in the default location and don't set a passphrase by hitting `enter` at the prompts (leave blank for no passphrase).

2. Copy the public key over to the other computer, replacing <user> and <host> with the respective username and host address of your machine:

`ssh-copy-id -oHostKeyAlgorithms='ssh-rsa' <user>@<host>`

The key here is to use the `-oHostKeyAlgorithms='ssh-rsa'` when SSH-ing as described in the ROS answers post above. Now when you use roslaunch to launch nodes on remote machines, roslaunch should be able to SSH into the machine without issues.

Repeat step 2 for every computer onboard Makobot, copying the RSA key to the Raspberry Pi, the Fitlet2, and the Jetson TX2.
