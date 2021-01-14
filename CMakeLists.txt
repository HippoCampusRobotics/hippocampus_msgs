cmake_minimum_required(VERSION 3.0.2)
project(hippocampus_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  geometry_msgs
)

add_message_files(
  FILES
  AttitudeTargetExt.msg
  GantryConfig.msg
  GantryMotorPosition.msg
  GantryPosition.msg
  PoseId.msg
  PoseIdStamped.msg
  GantryMotorVelocity.msg
  GantryVelocity.msg
  PathFollowerTarget.msg
  GantryMotorLimitSwitches.msg
)

add_service_files(
  FILES
  SetFloat.srv
  SetInt.srv
  GetFloat.srv
  GetInt.srv
)

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