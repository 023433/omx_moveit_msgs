cmake_minimum_required(VERSION 3.22)
project(omx_moveit_msgs)

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(moveit_task_constructor_core REQUIRED)

set(msg_files
	msg/PickAndPlaceStatus.msg
)


set(srv_files
	srv/ArmPlan.srv
	srv/ArmPlanExe.srv
)

rosidl_generate_interfaces(${PROJECT_NAME}
	${msg_files}
	${srv_files}
	DEPENDENCIES
	builtin_interfaces
  geometry_msgs
	moveit_task_constructor_core
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
