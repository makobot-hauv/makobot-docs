# Software Installation

The Makobot HAUV system uses the Robot Operating System (ROS) on Ubuntu Linux. These instructions will assume use of Ubuntu 18.04 and ROS Melodic, but other versions should work as well.  We recommend using Ubuntu for all computers in the system.  

## Install Ubuntu and ROS

### Raspberry Pi

The Raspberry Pi comes pre-installed with Raspbian (based on Debian). For using ROS, we recommend running Ubuntu Mate instead of Raspbian to avoid having to compile ROS from source. If you wish to run the default Raspbian image, follow the instructions on [Installing ROS Kinetic on the Raspberry Pi](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Kinetic%20on%20the%20Raspberry%20Pi) to build and install ROS from source.

If you choose to run Ubuntu Mate, install ROS Melodic using the usual [ROS installation instructions](http://wiki.ros.org/melodic/Installation) for Ubuntu.


### Fitlet2

Download the most recent [18.04 release of theAMD64 version of Ubuntu Mate](https://ubuntu-mate.org/download/amd64/) and install it on the Fitlet.

Follow the instructions to install [ROS Melodic](http://wiki.ros.org/melodic/Installation).

### Jetson TX2

TODO



## Install ROS Dependencies and Packages

Now that ROS is installed on all computers, we're going to install some dependencies and packages.

TODO: explanation of master computer packages to install vs packages needed on only some computers

TODO: which computer is ROS master? Raspberry Pi?

### Raspberry Pi

After installing ROS, install the following packages on the Raspberry Pi. (These instructions assume you are using Ubuntu Mate and are installing the packages in the apt repositories; Raspbian users must compile from source.)

```
sudo apt-get install python-catkin-tools ros-kinetic-joy ros-kinetic-robot-state-publisher ros-kinetic-robot-localization ros-kinetic-mavros ros-kinetic-mavros-extras ros-kinetic-sound-play
```

Install GeographicLib (needed for mavros) by downloading and running the installation script:

```
wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
./install_geographiclib_datasets.sh
```

Make sure you've created a catkin workspace by following the instructions in [ROS Environment Setup](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment).

In <your_catkin_workspace>/src, clone this repository:

```
git clone --recurse-submodules https://github.com/awilby/bluerov_ros.git
cd ..
catkin build
```

#### Install udev Rules

Copy the udev rules from the bluerov_robot and bluerov_teleop packages to `/etc/udev/rules.d/`. Reload udev rules by running `sudo udevadm control --reload`.


### Fitlet2

TODO

### NVIDIA Jetson TX2

TODO
