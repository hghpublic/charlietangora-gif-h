cmake_minimum_required(VERSION 4.4)

project(gif-h)

set(lib gif-h)
add_library(${lib} INTERFACE)

target_include_directories(${lib} INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
)

# demo

if(PROJECT_IS_TOP_LEVEL)
set(demo gif-h-demo)
add_executable(${demo})
target_sources(${demo} PRIVATE
    gif-h-demo.cpp
)
target_link_libraries(${demo} PRIVATE ${lib})
endif()
