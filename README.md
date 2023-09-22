# EE478 Final Project : Selfie Drone
Designed a Selfie Drone which operates based on the predefined pose detected!

It also draws heart shape in mid-air perfect for propose!

* Hardware Configuration

  * Camera: Realsense D435
  * Onboard-PC: Jetson Xavier NX2
  * FCC
  * ESC
  * Drone frame: carbon fiber frames
 
* Software Configuration
  * ROS
  * MAVROS
  * ORB-SLAM3
  * PoseNet

## Pose Estimation
pose estimation done by PoseNet (https://github.com/dusty-nv/jetson-inference, https://github.com/hynkis/ros_deep_learning/blob/master/src/node_posenet.cpp)

## Visual Odometry
Visual Odometry result by ORB-SLAM3 (https://github.com/yongeePark/ORB_SLAM3_ROS_Interface.git))

## Mission Planner
Our mission planner is based on FSM style, and the system flow is as follows

1) Take-off & wait before detection of target person with their right hand up
2) After detecting the target, drone approach the target so that target is located in the middle of the image frame and drone maintains specific distance from the target
3) If the target person raise both hand up, the drone takes a picture
4) When the person raise their left hand, the drone returns to the home position and wait
5) When the person raise their left leg, the drone safely lands

When detection of person raising their right leg, the drone draws heart in the air!

## Control
Our controller is P controller and our drone remains specific yaw angle throughout the process

## ETC
