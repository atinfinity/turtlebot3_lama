# turtlebot3_lama

## Introduction
This is a package to use [iris_lama_ros](https://github.com/iris-ua/iris_lama_ros) with TurtleBot3(Gazebo).

## Requirements

- ROS Melodic

## Build

```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ git clone https://github.com/iris-ua/iris_lama
$ git clone https://github.com/iris-ua/iris_lama_ros
$ git clone https://github.com/atinfinity/turtlebot3_lama
$ cd ..
$ catkin config --extend /opt/ros/melodic
$ catkin build
```

## Mapping
### Launch Gazebo

```
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

### Launch LaMa ROS for Mapping

```
$ roslaunch turtlebot3_lama_slam turtlebot3_lama_slam.launch slam_methods:=slam2d
```

### Launch Teleop

```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

### Save Map

```
$ mkdir ~/maps
$ rosrun map_server map_saver -f  ~/maps/world_map
```

## Navigation

### Launch Gazebo

```
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

### Launch LaMa ROS for Navigation

```
$ roslaunch turtlebot3_lama_navigation turtlebot3_lama_navigation.launch map_file:=$HOME/maps/world_map.yaml
```

