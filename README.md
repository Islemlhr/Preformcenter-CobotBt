# simulation


The Panda Simulation package was written for ROS melodic by [Erdalpekel](https://github.com/erdalpekel) </br>  and runs on Ubuntu 18.04. Run the following commands to install all the Packages :

 *create a new Workspace first :*

``` bash
mkdir -p catkin_ws/src
cd catkin_ws/src

```
* clone these Packages :*

``` bash
git clone https://github.com/Islemlhr/Preformcenter-CobotBt.git
git clone https://github.com/Islemlhr/Franka_ros.git
cd ..
sudo apt-get install libboost-filesystem-dev
rosdep install --from-paths src --ignore-src -y --skip-keys libfranka
cd ..
```
Note that it is also important to build the *libfranka* library from source and pass its directory to *catkin_make* when building this ROS package, as described in [this tutorial] (https://frankaemika.github.io/docs/installation.html#building-from-source) and also for the camera (added in [Franka-ros/Franka-description]) this package must be installed from  [realsense-ros](https://github.com/IntelRealSense/realsense-ros.git) </br>

Build the catkin workspace and run the simulation:
```
catkin_make -j4 -DCMAKE_BUILD_TYPE=Release -DFranka_DIR:PATH=/path/to/libfranka/build
source devel/setup.bash
roslaunch panda_simulation simulation.launch
```

