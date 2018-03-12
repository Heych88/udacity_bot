# ROS Localisation and Navigation using Adaptive Monte Carlo Localisation (AMCL)

This repository contains a Robot Operating System (ROS) implementation of a differential drive Gazebo model for uses with the ROS navigation stack.
The model uses the Adaptive Monte Carlo Localisation (AMCL) method for localisation with the Elastic band planner method to navigate to goal locations.

![Differential drive robot model](images/diff-drive-bot.png)

## Project website

This repository has an accompanying project page, contains the theory and details behind the code. It can be found [here](https://www.haidynmcleod.com/ros-diff-drive-navigation).

## Prerequisites

1. [Ubuntu](https://www.ubuntu.com/) OS or [debian](https://www.debian.org/distrib/)

2. Robot Operating System (ROS). Installation instructions can be found [here](http://wiki.ros.org/ROS/Installation).

3. Install ROS nodes required for the local and global planners, amcl, maps and motor control for the navigation stack.

```sh
$ sudo apt-get install ros-kinetic-move-base
$ sudo apt-get install ros-kinetic-map-server
$ sudo apt-get install ros-kinetic-amcl
$ sudo apt-get install ros-kinetic-eband-local-planner
$ sudo apt-get install ros-kinetic-global-planner
$ sudo apt-get install ros-kinetic-carrot-planner
```

## Installing

Clone this repository in your catkin workspace 'src/' folder.

```sh
$ cd ~/catkin_ws/src/
$ git clone https://github.com/Heych88/udacity_bot.git
```

Build the project:
```sh
$ cd ~/catkin_ws
$ catkin_make
```

If you haven’t already, the following line can be added to your .bashrc to auto-source all new terminals
```
source ~/catkin_ws/devel/setup.bash
```

## Run the Code

In a terminal window, type the following,
```sh
$ cd ~/catkin_ws
$ roslaunch udacity_bot udacity_world.launch
```

In a new terminal, run the 'amcl.launch' file.
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ roslaunch udacity_bot amcl.launch
```

Gazebo and Rviz will load and you should arrive at a result similar to the below.

![Gazebo & RViz with costmap](images/RvizGazebo.png)

###### Testing 

In a new terminal window, type the following,
```sh
$ cd ~/catkin_ws
$ source devel/setup.bash
$ rosrun udacity_bot navigation_goal
```
You should arrive at a result similar to the below.

![navigation to a goal location](images/nav_goal.png)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
