# ck9_gazebo
CK-9's Gazebo simulation package.

## Pre-requisites:
1. Ubuntu 16.04
2. ROS Kinetic Kame (For installation steps: http://wiki.ros.org/kinetic/Installation/Ubuntu)

## This repo contains:
1. CK-9 URDF model for simulation (differential drive robot with two motors and LiDaR)
2. Gazebo sim launch file
3. teleop launch file
4. gmapping launch file (coming soon)
5. navigation pkg and launch file 

## Steps
- ```cd catkin_ws/src```
- ```git clone https://github.com/centauri-robotics/ck9_gazebo```
- ```cd ~/catkin_ws```
- ```catkin_make```
- ```source ~/catkin_ws/devel/setup.bash```
- To start the gazebo simulation and rviz with CK-9, type:
```roslaunch ck9_gazebo ck9_gazebo.launch```
- To move CK-9 around with teleop: ```roslaunch ck9_simple_control ck9_control_teleop.launch```
- For gmapping, first launch the above two files and then: ```rosrun gmapping slam_gmapping```
and then move around your CK-9 with teleop.
- Save the map using the command ```rosrun map_server map_saver -f map_name```
- To run autonomous navigation, first launch ```roslaunch ck9_gazebo ck9_gazebo.launch``` and then ```roslaunch ck9_navigation ck9_navigation.launch map_file:=/home/username/path_to_map.yaml``` (The default map is the willowgarage_gmapping.yaml provided in this repo's map folder)
