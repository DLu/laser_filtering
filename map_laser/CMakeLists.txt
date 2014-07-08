cmake_minimum_required(VERSION 2.8.3)
project(map_laser)

find_package(catkin REQUIRED COMPONENTS rospy sensor_msgs nav_msgs tf std_msgs)

catkin_package(
    CATKIN_DEPENDS rospy sensor_msgs nav_msgs tf std_msgs
)

