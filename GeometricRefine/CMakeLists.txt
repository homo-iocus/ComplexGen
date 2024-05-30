cmake_minimum_required(VERSION 3.12)

project(GeometricRefine)
add_subdirectory(${CMAKE_SOURCE_DIR}/allquadricsdirect)
add_subdirectory(${CMAKE_SOURCE_DIR}/yaml-cpp)

set(CMAKE_TOOLCHAIN_FILE "${CMAKE_SOURCE_DIR}/vcpkg/scripts/buildsystems/vcpkg.cmake"
    CACHE STRING "Vcpkg toolchain file")

set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH};${CMAKE_SOURCE_DIR}/vcpkg/installed/x64-linux")

find_package(libigl REQUIRED)

include_directories(${CMAKE_SOURCE_DIR}/yaml-cpp/include/yaml-cpp)
include_directories(${CMAKE_SOURCE_DIR}/eigen3)
include_directories(${CMAKE_SOURCE_DIR}/vcpkg/installed/x64-linux/include)

add_subdirectory(${CMAKE_SOURCE_DIR}/GeometricRefine)
