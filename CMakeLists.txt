cmake_minimum_required(VERSION 3.0.0)
project(uabDec VERSION 0.1.0)

set(CMAKE_VS_PLATFORM_TOOLSET_HOST_ARCHITECTURE x86)

cmake_policy(SET CMP0074 NEW)
find_package(Boost REQUIRED COMPONENTS system filesystem)

set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /MT")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MTd")

add_executable(uabDec main.cpp AssetDecoder.cpp)
include_directories(${Boost_INCLUDE_DIRS})
target_link_directories(uabDec PUBLIC ${Boost_LIBRARY_DIRS})

message(${CMAKE_VS_PLATFORM_TOOLSET_HOST_ARCHITECTURE})