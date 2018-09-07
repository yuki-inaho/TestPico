cmake_minimum_required(VERSION 3.5)
project(TestPico)
add_executable(TestPico TestPico.cpp)

set(CMAKE_CXX_COMPILER "g++")
set(CMAKE_CXX_FLAGS "-O0 -std=c++11")

find_package(PkgConfig REQUIRED)

pkg_check_modules(OpenCV opencv REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(TestPico ${OpenCV_LIBRARIES})

pkg_check_modules(Royale royale REQUIRED)
include_directories(${Royale_CFLAGS})
target_link_libraries(TestPico ${Royale_LDFLAGS})
