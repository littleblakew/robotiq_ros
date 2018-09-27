# robotiq_ros

This repo holds source code for ROS.

# Prerequisites
1. Install ROS.
2. Install Moveit and other dependencies.
```
sudo apt-get install ros-<distro>-moveit ros-<distro>-moveit-full-pr2 ros-<distro>-soem ros-<distro>-controller-manager ros-<distro>-socketcan-bridge
```
3. Install UR packages.
```
sudo apt-get install ros-<distro>-universal-robot
```
# Installation
1. Clone the repo into your workspace.
```
cd <YOUR WORKSPACE>/src/
git clone https://github.com/littleblakew/robotiq_ros.git
```
2. Compile the packages.
```
cd ..
catkin_make
```
3. Install robotiq_modbus_tcp. 
```
rosdep install robotiq_modbus_tcp 
```

# Configuration
## Gripper
See: [S-Gripper][]

## FT 300 
1. Enter the robotiq_ros folder
2. Copy the rule "udev/52-ftdi.rules" into "/etc/udev/rules.d"
```
sudo cp /robotiq_force_torque_sensor/udev/52-ftdi.rules /etc/udev/rules.d
```
3. Reconnect the usb of FT300.
4. Check the new name of device of FT300, which is supposed to be "/dev/ftdi_XXXXXXXX".
5. Replace the old name of device of FT300 in "robotiq_force_torque_sensor/launch/ft_300.launch" with the new name of device of FT300.

# Usage
## Gripper
```
rosrun robotiq_s_model_control SModelTcpNode.py 192.168.1.11 
rosrun robotiq_s_model_control SModelSimpleController.py 
```
## FT 300
```
roslaunch robotiq_force_torque_sensor ft_300.launch
```
[ROS force_torque_tools]: http://wiki.ros.org/force_torque_tools/Tutorials/Force-torque%20sensor%20calibration
[S-Gripper]: https://us.v-cdn.net/6027406/uploads/editor/8j/gmmvz5b1kx3j.pdf


# Reference
1. https://github.com/ros-industrial/robotiq
2. https://github.com/ibaranov-cp/husky_UR_accessories
