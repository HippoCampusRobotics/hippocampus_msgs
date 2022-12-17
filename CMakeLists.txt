cmake_minimum_required(VERSION 3.0.2)
project(hippocampus_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  geometry_msgs
)

file(GLOB_RECURSE MSG_FILES
  RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}/msg"
  "*.msg"
)

file(GLOB_RECURSE SRV_FILES
  RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}/srv"
  "*.srv"
)

if(MSG_FILES)
  add_message_files(
    FILES
    ${MSG_FILES}
  )
endif()

if(SRV_FILES)
  add_service_files(
    FILES
    ${SRV_FILES}
  )
endif()

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

catkin_package(CATKIN_DEPENDS
  message_runtime
  std_msgs
  geometry_msgs
)


include_directories(${catkin_INCLUDE_DIRS})
