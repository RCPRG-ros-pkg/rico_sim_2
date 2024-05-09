cmake_minimum_required(VERSION 3.8)
project(tiago_simulation_bringup)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(ament_cmake_python REQUIRED)
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

# ------------------------------CPP---------------------------------

# Include C++ "include" directory
include_directories(include)

# ----------------------------PYTHON---------------------------------

# Install Python modules
ament_python_install_package(${PROJECT_NAME})

install(DIRECTORY 
  launch
  maps
  rviz
  config
  DESTINATION share/${PROJECT_NAME})

ament_package()
