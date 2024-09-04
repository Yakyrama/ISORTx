# ISORTx
ISORTx : Dual robotics arms used for unfolding cloth

The goal of this repository is to be a guide for a future use of the dual arms to unfold the different type of cloth.

<p align="center">
  <img src="https://github.com/Yakyrama/ISORTx-Dual-robotics-arms/blob/b3ebf2b6459518d62e2998d3982dbbf971a74ea0/github_image/both_robot_standing_still.png?raw=true" alt="Dual robotics arms staying still"/>
</p>

First of all, The goal of this project is to unfold the cloth using two robotics arms of Trossens Robotics: the WidowX250s.
In order to do this, the robotics arms need to grab the cloth. It means that they need to see how the cloth is laying to do,
We use a d345 to detect the cloths and use segment anything to isolate the hard part of the cloth such as zipper or buttons.

First the version of Ubuntu used was Ubuntu 22.04 Jammy and the version of ros was ROS2 humble.

Now that the goal of this repositery was laid out, the installation process can begin:

First, we install python and git in order to clone it:

```1st install  
sudo apt install python3
sudo apt install python3-pip
sudo apt-get install git-all
```
Then we create a workspace:

```Environement and src
mkdir isortx_ws
cd isortx_ws
mkdir src
```

After, that we just need to clone the repository:

```Cloning the repo
git clone https://github.com/Yakyrama/ISORTx-Dual-robotics-arms.git
colcon build
source install/setup.bash
colcon build
```

Next, we need to install the libraries required to make the program work:

```Installing the requirements
pip install -r requirements.txt
```

And now is the fun part: the Testing part.
So first, open 2 terminals and in both paste the following command:
```
colcon build
source install/setup.bash
colcon build
```

And then in one terminal paste this:
```
ros2 launch interbotix_xsarm_dual xsarm_dual.launch.py
```
Wait a bit for the dual robotic arms to spawn in Rviz,
Then in the other terminal paste the followijng command:
```
ros2 run interbotix_xsarm_dual xsarm_dual.py
```
With this, there should be two robotic arms moving in rviz in a movement that look like a cloth being picked up and somewhat unfolded and then putting it back down.

<p align="center">
  <img src="https://github.com/Yakyrama/ISORTx-Dual-robotics-arms/blob/b3ebf2b6459518d62e2998d3982dbbf971a74ea0/github_image/Both_robots_moving.png?raw=true" alt="Dual robotics arms moving"/>
</p>

This is the end of this GitHub.
