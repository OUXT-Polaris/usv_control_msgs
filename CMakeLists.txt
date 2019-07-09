cmake_minimum_required(VERSION 2.8.3)
project(usv_control_msgs)


find_package(catkin REQUIRED COMPONENTS
  message_generation
  message_runtime
  std_msgs
)

add_message_files(
  FILES
  AzimuthThrusterCatamaranDrive.msg
  AzimuthThrusterCatamaranDriveStamped.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
)

foreach(dir msg)
  install(DIRECTORY ${dir}/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)