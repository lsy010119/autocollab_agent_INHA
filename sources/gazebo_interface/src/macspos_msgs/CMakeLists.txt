cmake_minimum_required(VERSION 3.8)
project(macspos_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

set(msg_files
"msg/AgentExternalState.msg"
"msg/AgentInternalSetpoint.msg"
"msg/AgentInternalState.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
    ${msg_files}
    DEPENDENCIES builtin_interfaces std_msgs geometry_msgs
)

    
ament_export_dependencies(rosidl_default_runtime std_msgs geometry_msgs)
ament_package()
