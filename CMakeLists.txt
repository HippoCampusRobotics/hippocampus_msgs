cmake_minimum_required(VERSION 2.8.3)
project(hippocampus_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
)

add_message_files(
  FILES
)

#add_service_files(
#  FILES
#)

generate_messages(
  DEPENDENCIES
)

catkin_package(CATKIN_DEPENDS
  message_runtime
)


include_directories(${catkin_INCLUDE_DIRS})
