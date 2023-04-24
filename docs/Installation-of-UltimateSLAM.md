# Installation of Ultimate SLAM
Updated instructions for Noetic. Please see original [repo](github.com/uzh-rpg/rpg_ultimate_slam_open) for original instructions.

This installation guide was tested with Noetic on Ubuntu 20.04

### Dependencies


    sudo apt update && sudo apt install liblapack-dev libblas-dev git python3-catkin-tools python3-vcstool -y


### Install

First, we need to create a [catkin](http://wiki.ros.org/catkin) workspace for UltimateSLAM and initialize it:

    mkdir -p ~/uslam_ws/src && cd ~/uslam_ws
    catkin init
    

Make sure you have ROS sourced and continue:

    catkin config --extend /opt/ros/$ROS_DISTRO --cmake-args -DCMAKE_BUILD_TYPE=Release

Clone the UltimateSLAM repository and run `vcstool` to automatically import the dependencies:

    cd src/
    git clone http://github.com/discoimp/rpg_ultimate_slam_open.git
    vcs-import < rpg_ultimate_slam_open/dependencies.yaml

Finally, build UltimateSLAM:

    catkin build ze_vio_ceres

This will take some time (a couple of minutes at least). In case of errors, see the Troubleshooting section below.

If building succeeds, congrats! You have installed UltimateSLAM. Your next step will be to [run some examples](Run-Examples.md) to test your setup.
