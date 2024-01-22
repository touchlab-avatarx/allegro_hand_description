cmake_minimum_required(VERSION 2.8.3)
project(allegro_hand_description)

find_package(catkin REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  xacro
)

catkin_package(
)

install(DIRECTORY .
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/
  FILES_MATCHING
  PATTERN "*.xacro"
  PATTERN "*.world"
  PATTERN "*.STL"
)

install(DIRECTORY launch config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

file(GLOB xacro_files urdf/*.urdf.xacro)
xacro_add_files(${xacro_files} TARGET urdf INSTALL)

install(DIRECTORY urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
