cmake_minimum_required(VERSION 2.8.3)
project(cob_rocon_multimaster)

find_package(catkin REQUIRED)
catkin_package()

### INSTALL ###
install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
  