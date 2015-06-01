cmake_minimum_required(VERSION 2.8.3)
project(rocon_nao)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  nao_bringup
  rocon_app_manager
  rocon_apps
)

catkin_package()

catkin_add_env_hooks(25.nao SHELLS sh DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/env-hooks)

install(DIRECTORY
  launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
