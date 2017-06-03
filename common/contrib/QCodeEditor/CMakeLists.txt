#==============================================================================
# CMakeLists file for QCodeEditor
#==============================================================================
cmake_minimum_required(VERSION 3.0)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CURR_TARGET QCodeEditor)

set(CURR_TARGET_SOURCES "${CURR_TARGET}_SOURCES")
set(CURR_TARGET_FORMS "${CURR_TARGET}_FORMS")
set(CURR_TARGET_HEADERS "${CURR_TARGET}_HEADERS")
set(CURR_TARGET_RESOURCES "${CURR_TARGET}_RESOURCES")

include_directories(src)
include_directories(inc)
include_directories(res)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
find_package(Qt5Widgets REQUIRED)

#==============================================================================
# Include Source Files
#==============================================================================
file(GLOB CURR_TARGET_SOURCES "src/*.cpp")
file(GLOB CURR_TARGET_FORMS "src/*.ui")
file(GLOB CURR_TARGET_HEADERS "inc/*.h*")
file(GLOB CURR_TARGET_RESOURCES "resx/*.qrc")

#==============================================================================
# Add Executable
#==============================================================================
add_library(${CURR_TARGET}
               ${LIBRARY_MODE}
               ${CURR_TARGET_SOURCES}
               ${CURR_TARGET_HEADERS}
               ${CURR_TARGET_FORMS}
               ${CURR_TARGET_RESOURCES}
               )

#==============================================================================
# Add Dependencies
#==============================================================================
qt5_use_modules(${CURR_TARGET} Widgets)
#add_dependencies(${CURR_TARGET} )


