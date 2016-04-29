################################################################
################################################################
CMAKE_MINIMUM_REQUIRED (VERSION 2.8)

SET (target "driver_assist")
PROJECT (${target} CXX)

# define source files
FILE (GLOB src *.hpp *.cpp)

# add current directory to the cmake_module_path for reading the "findiconv.cmake"
LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR} )

#required packages
find_package(OpenCV 2.4 REQUIRED)


INCLUDE_DIRECTORIES (${OPENCV_INCLUDE_DIR})

ADD_EXECUTABLE (${target} ${src})
TARGET_LINK_LIBRARIES (${target} ${OpenCV_LIBS} )




