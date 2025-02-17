cmake_minimum_required(VERSION 3.0)

add_compile_options(
  -Wall
  #-Werror
  -std=c++11
-g
)
# else probably running unit tests with catch on a host
project(NMEA2000)

set(NMEA_DIR "${CMAKE_SOURCE_DIR}/NMEA2000")

file(GLOB_RECURSE ${PROJECT_NAME}_SRC 
    "${NMEA_DIR}/src/*.cpp" 
)

set(${PROJECT_NAME}_INC_DIR
  "${NMEA_DIR}/src" )

add_library(${PROJECT_NAME} OBJECT ${${PROJECT_NAME}_SRC})
