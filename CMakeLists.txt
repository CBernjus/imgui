cmake_minimum_required(VERSION 3.6)
project(imgui)

add_library(
        imgui STATIC
        imconfig.h
        imgui.cpp
        imgui.h
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_internal.h
        imgui_tables.cpp
        imgui_widgets.cpp
        imstb_rectpack.h
        imstb_textedit.h
        imstb_truetype.h
        backends/imgui_impl_glfw.cpp
        backends/imgui_impl_glfw.h
        backends/imgui_impl_opengl3.cpp
        backends/imgui_impl_opengl3.h
)

# TODO: do something to prevent available scope <imgui.h> instead of <imgui/imgui.h>
target_include_directories(imgui PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(imgui SYSTEM INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(imgui glfw)