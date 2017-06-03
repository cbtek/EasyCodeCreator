
#==============================================================================
# CMakeLists file for test_EasyCodeCreator
#==============================================================================
cmake_minimum_required(VERSION 3.0)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CURR_TARGET test_EasyCodeCreator)
project(${CURR_TARGET})
set(CURR_TARGET_SOURCES "${CURR_TARGET}_SOURCES")
set(CURR_TARGET_HEADERS "${CURR_TARGET}_HEADERS")

include_directories(inc)
include(${CMAKE_MODULE_PATH}/flags.cmake)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

#==============================================================================
# Include Source Files
#==============================================================================
file(GLOB CURR_TARGET_SOURCES "src/*.cpp")
file(GLOB CURR_TARGET_HEADERS "inc/*.h*")

#==============================================================================
# Add Executable
#==============================================================================
add_executable(${CURR_TARGET}
               ${CURR_TARGET_SOURCES}
               ${CURR_TARGET_HEADERS}
               )

#==============================================================================
# Add Dependencies
#==============================================================================

#add_dependencies(${CURR_TARGET} common_utils )

#==============================================================================
# Target Link Libraries
#==============================================================================
#target_link_libraries(${CURR_TARGET} common_utils )