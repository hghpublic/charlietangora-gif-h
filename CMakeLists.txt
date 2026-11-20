cmake_minimum_required(VERSION 4.4)

project(gif-h-demo)

include(FetchContent)

set(lib gif-h)
FetchContent_Declare(${lib}
    GIT_REPOSITORY https://github.com/hghpublic/charlietangora-gif-h.git
    GIT_TAG dev/0
    GIT_SHALLOW TRUE
)
FetchContent_MakeAvailable(${lib})

# demo

set(demo gif-h-demo)
add_executable(${demo})
target_sources(${demo} PRIVATE
    gif-h-demo.cpp
)
target_link_libraries(${demo} PRIVATE ${lib})
