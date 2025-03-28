cmake_minimum_required(VERSION 3.0.2)
project(trajectory_saver_msg)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  geometry_msgs
  sensor_msgs
  manipulation_msgs
  moveit_msgs
  trajectory_planning_msg
  message_generation
)
add_service_files(
    FILES
    AddPose.srv
    AddTrajectory.srv
    GetListOfPoses.srv
    GetPose.srv
    GetTrajectory.srv
    RemovePose.srv
    RemoveTrajectory.srv
)

generate_messages(
    DEPENDENCIES
    std_msgs
    geometry_msgs
    sensor_msgs
    manipulation_msgs
)
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES trajectory_saver_msg
  CATKIN_DEPENDS message_runtime
#  DEPENDS system_lib
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
