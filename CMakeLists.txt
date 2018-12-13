cmake_minimum_required(VERSION 3.0)

set(PROJECT_NAME "smartplug")

project(${PROJECT_NAME})

################################################################################
# Options
################################################################################

message(STATUS)
message(STATUS "${PROJECT_NAME} Configuration:")
message(STATUS "CMAKE_BUILD_TYPE              = ${CMAKE_BUILD_TYPE}")
message(STATUS "CMAKE_INSTALL_PREFIX          = ${CMAKE_INSTALL_PREFIX}")
message(STATUS)
message(STATUS "IOTIVITY_INCLUDE_PATH         = ${IOTIVITY_INCLUDE_PATH}")
message(STATUS)
message(STATUS "IOTIVITY_LIB_PATH             = ${IOTIVITY_LIB_PATH}")
message(STATUS)


################################################################################
# Compiler flags
################################################################################

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -Wall")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")

################################################################################
# Definitions
################################################################################

add_definitions(-DTB_LOG)

################################################################################
# Includes
################################################################################

include_directories(
	${IOTIVITY_INCLUDE_PATH}/c_common
	${IOTIVITY_INCLUDE_PATH}/resource
	${IOTIVITY_INCLUDE_PATH}/resource/stack
	.
)

################################################################################
# Link directories
################################################################################

link_directories(
	${IOTIVITY_LIB_PATH}
)

################################################################################
# Sources
################################################################################

add_subdirectory(src)
