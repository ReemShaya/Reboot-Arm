# Reboot-Arm 


## Introduction

Welcome to my first artificial intelligence project. In this project I installed VMware Workstation 16 Player on my PC, installed Ubuntu 20.04 then configured ROS and finally installed packages for the arm. I will write down the steps for installing the rose system and installing the packages for the arm.



## Commands to Install The ROS System


All of the following commands should be written one by one in the Terminal


To prepare the computer to install the ROS system :

```sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' ```


To open the key server on the computer :


```sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654 -- ``` 

```sudo apt-get update```


To install the ROS system :

```sudo apt-get install ros-noetic-desktop-full```

```apt-cache search ros-noetic```

```echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc```

```source ~/.bashrc```

```sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential```

```sudo apt install python-rosdep```

```sudo rosdep init```

```rosdep update```

```sudo apt-get install ros-noetic-catkin```

To install catkin to be able to create a workspace :

```mkdir -p ~/catkin_ws/src```

```cd ~/catkin_ws/```

```catkin_make```

```cd ~/catkin_ws/src```



## Commands to Install The Package of The Arm


To get to the packages of the robot arm :

```git clone https://github.com/smart-methods/arduino_robot_arm.git``` 

```cd ~/catkin_ws```

```rosdep install --from-paths src --ignore-src -r -y```

```sudo apt-get install ros-noetic-moveit```

```sudo apt-get install ros-noetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui```

```sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher```

```sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control```

Type this command in the terminal, then it will ask you for the password, and when you type the password, it will open another page for you :

```sudo nano ~/.bashrc```


Here I have to change the source path, I will put it in the bashrc. Because the bashrc file is the one that runs as soon as you start the Ubuntu system and then runs the internal systems and programs .

So at the end of the (bashrc) file add the follwing line :

```(source /home/ReemShaya/catkin_ws/devel/setup.bash)```

then (ctrl + o) then (enter) then (ctrl + x)

```source ~/.bashrc```



## Launching the Arm

Type This Command in The Terminal :

`
roslaunch robot_arm_pkg check_motors.launch
`

Then the arm will work like the following picture

![image](https://user-images.githubusercontent.com/85775606/123556569-992e1d80-d794-11eb-89e5-2d8c643db191.png)


