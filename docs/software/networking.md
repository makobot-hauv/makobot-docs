# Networking

## Set up Networking on fitlet2

todo: set static IP

subnet of each NIC

## Set up Networking on Raspberry Pi

todo: set static IP

## Set up Networking on Jetson TX2

todo: set static IP 


## Edit Hosts File

Edit `/etc/hosts` file and add the following lines:

```
192.168.2.2     makobot-pi
192.168.2.13    fitlet2-1
192.168.2.169   jetson-tx2
```


## Set up SSH Keys

As per the ROS issue described <a href="https://answers.ros.org/question/244060/roslaunch-ssh-known_host-errors-cannot-launch-remote-nodes/"  target="_blank">here</a>, we have to set up SSH keys so that roslaunch can correctly SSH into the different machines. Do this step on the topside computer as that is where we will be launching the ROS processes from.

1. Generate the RSA key pair as usual:

`ssh-keygen -t rsa`

Save the file in the default location and don't set a passphrase by hitting `enter` at the prompts (leave blank for no passphrase).

2. Copy the public key over to the other computer, replacing <user> and <host> with the respective username and host address of your machine:

`ssh-copy-id -oHostKeyAlgorithms='ssh-rsa' <user>@<host>`

The key here is to use the `-oHostKeyAlgorithms='ssh-rsa'` when SSH-ing as described in the ROS answers post above. Now when you use roslaunch to launch nodes on remote machines, roslaunch should be able to SSH into the machine without issues.

Repeat step 2 for every computer onboard Makobot, copying the RSA key to the Raspberry Pi, the Fitlet2, and the Jetson TX2.
