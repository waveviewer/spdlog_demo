cmake_minimum_required(VERSION 3.21)
project(spdlog_demo)

set(CMAKE_CXX_STANDARD 14)

add_library(spdlog INTERFACE)
target_include_directories(
        spdlog INTERFACE
        "${CMAKE_SOURCE_DIR}/Libraries"
)

find_package(Threads)

add_executable(spdlog_demo
        sources/main.cpp
        )
target_link_libraries(spdlog_demo spdlog ${CMAKE_THREAD_LIBS_INIT})