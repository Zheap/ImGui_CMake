cmake_minimum_required(VERSION 3.10)

project(imgui_cmake VERSION 1.0)

add_executable(imgui_cmake main.cpp)

set_property(TARGET imgui_cmake PROPERTY CXX_STANDARD 17)

add_subdirectory(vendor/glfw)
add_subdirectory(vendor/imgui)

target_link_libraries(imgui_cmake
    PUBLIC
    imgui
)