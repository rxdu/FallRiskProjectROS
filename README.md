FallRiskProjectROS
==================

[RIVeR](http://robot.wpi.edu) Lab, WPI


1.Launch Files
------------------

You can find most launch files in fall_risk_assessment package.

Turn on the turtlebot and run both mjpeg server and rosbridge server:

```
roslaunch fall_risk_assessment fall_risk_demo.launch 
```

Set up a webcam on a computer with MJPEG Server and ROSBridge running:

```
roslaunch fall_risk_assessment pc_rosbridge_mjpeg.launch 
```

Draw a circle with distance on a image from kinect:

```
roslaunch fall_risk_assessment kinect_dist_circle.launch 
```

Draw reference lines on a image from kinect:

```
roslaunch fall_risk_assessment kinect_ref_line.launch 
```

2.Source Folder
-------------------

**fall_risk_assessment**: mainly launch files at present

**kinect depth**: nodes about 3d depth/distance processing/vision

**kinect_image**: nodes about 2d image processing/vision

**uvc_camera**: catkinized version of tutorialROSOpenCV, mainly used for testing with webcam when robot is not available

3.Setting UP Your Workspace
-------------------

* Create your workspace

```
mkdir -p ~/fallrisk_ws/src
cd ~/fallrisk_ws/src
catkin_init_workspace
cd ~/fallrisk_ws/
catkin_make
source devel/setup.bash
```

* Setting Up .bashrc File

```
echo source ~/fallrisk_ws/devel/setup.bash >> ~/.bashrc
. ~/.bashrc
```

```
cd ~/fallrisk_ws/src
wstool init
wstool set fall_risk_project_ros https://github.com/rxdu/FallRiskProjectROS.git --git
wstool update
```

* Compile project

```
cd ~/fallrisk_ws
catkin_make
```

3.Installing mjpeg server and rosbridge server for ROS Hydro
-------------------

```
sudo apt-get install ros-hydro-mjpeg-server
sudo apt-get install ros-hydro-rosbridge-server
```

4.Using OpenCV in a ROS node
------------------

This article can give you a idea about how it works:

http://siddhantahuja.wordpress.com/2011/07/20/working-with-ros-and-opencv-draft/

But it is out of dated and using the old rosbuild rather than catkin. 

If you still want to follow this article, make sure to make adjustments.

For example, the tutorial gives:

```
$ sudo apt-get install ros-fuerte-camera-umd
```

Then you need to change it to:

```
$ sudo apt-get install ros-groovy-camera-umd
```

Follow this tutorial to lean how to use cv_bridge

http://wiki.ros.org/cv_bridge/Tutorials/UsingCvBridgeToConvertBetweenROSImagesAndOpenCVImages

