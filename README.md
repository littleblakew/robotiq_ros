# robotiq_ros

This repo holds source code for ROS (indigo).

# Prerequisites
1. Install Ros (indigo). See: [ROS indigo][]
2. Install Moveit and other dependencies.
```
sudo apt-get install ros-indigo-moveit ros-indigo-moveit-full-pr2 ros-indigo-soem ros-indigo-controller-manager ros-indigo-socketcan-bridge
```
# Configuration
1. Enter the robotiq_ros folder
2. Copy the rule "52-ftdi.rules" into "/etc/udev/rules.d"
```
sudo cp /robotiq_force_torque_sensor/udev/52-ftdi.rules /etc/udev/rules.d
```
3. Reconnect the usb of FT300.
4. Check the new name of device of FT300, which is supposed to be "/dev/ftdi_XXXXXXXX".
5. Replace the old name of device of FT300 in "/robotiq_force_torque_sensor/launch/ft_300.launch" with the new name of device of FT300.

# Usage
[Gripper]

[F/T Sensor]

[ROS indigo]: http://wiki.ros.org/indigo/Installation/Ubuntu

# Reference
https://github.com/ros-industrial/robotiq
https://github.com/ibaranov-cp/husky_UR_accessories
