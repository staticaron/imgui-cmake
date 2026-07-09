cmake_minimum_required(VERSION 3.19)

project(imgui)

set(IMGUI_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/imconfig.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_internal.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp"

    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp"
)

add_library(imgui STATIC "${IMGUI_SOURCES}")

target_include_directories(imgui PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}"
)

target_link_libraries(imgui glfw glad)
