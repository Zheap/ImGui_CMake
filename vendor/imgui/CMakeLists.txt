add_library(imgui STATIC)

set_property(TARGET imgui PROPERTY CXX_STANDARD 17)

target_sources(imgui
    PRIVATE
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui.cpp

    backends/imgui_impl_opengl3.cpp
    backends/imgui_impl_glfw.cpp
)

find_package(OpenGL REQUIRED)
target_link_libraries(imgui 
    PUBLIC
    glfw
    ${OPENGL_LIBRARIES}
)

target_include_directories(imgui
    PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)