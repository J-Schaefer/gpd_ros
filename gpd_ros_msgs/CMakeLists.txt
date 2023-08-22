cmake_minimum_required(VERSION 3.0.2)
project(gpd_ros_msgs)

set(MSG_DEPS
  std_msgs
  geometry_msgs
  sensor_msgs
)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  ${MSG_DEPS}
  message_generation
  rospy
)

## System dependencies are found with CMake's conventions
# find_package(Boost REQUIRED COMPONENTS system)


################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
set(MSG_FILES
   FILES
   CloudIndexed.msg
   CloudSamples.msg
   CloudSources.msg
   GraspConfig.msg
   GraspConfigList.msg
   SamplesMsg.msg
)

## Generate services in the 'srv' folder
set(SRV_FILES
   FILES
   detect_grasps.srv
)

add_message_files(DIRECTORY msg FILES ${MSG_FILES})
add_service_files(DIRECTORY srv FILES ${SRV_FILES})

## Generate added messages and services with any dependencies listed here
generate_messages(DEPENDENCIES ${MSG_DEPS})


###################################
## catkin specific configuration ##
###################################
catkin_package(DEPENDS ${MSG_DEPS} message_runtime)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
