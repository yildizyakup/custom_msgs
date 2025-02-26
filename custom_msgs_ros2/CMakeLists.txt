cmake_minimum_required(VERSION 3.5)
project(custom_msgs)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 11)
endif()
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

# List your message files here
set(msg_files
  "msg/MyDetection3DArray.msg"
  "msg/MyDetection3D.msg"
  "msg/MyBoundingBox3D.msg"
  "msg/DetectionResult.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES std_msgs geometry_msgs
)

ament_package()

