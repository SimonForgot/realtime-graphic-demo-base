# CMake mininum version request
cmake_minimum_required (VERSION 3.14)

# project info
project(base_proj)

#global compiler settings
if(MSVC)
    add_compile_options(/W3 /Wx)
else ()
    add_compile_options(-W -std=c++11 -O0)
    #-g:for debug
    #-Wall:generate warning
    #-W:do not generate warning
    #-Werror:treat warning as error
endif()

find_package(glfw3 3.3 REQUIRED)
add_subdirectory(ext)

add_executable(${PROJECT_NAME} main.cpp ${GLAD_SRC}/glad.c  #glad/src/glad.c
        ${IMGUI_SRC}/imgui.cpp
         ${IMGUI_SRC}/imgui_draw.cpp
           ${IMGUI_SRC}/imgui_demo.cpp
             ${IMGUI_SRC}/imgui_widgets.cpp
        ${IMGUI_SRC}/imgui_impl_glfw.cpp
        ${IMGUI_SRC}/imgui_impl_opengl3.cpp
    )
target_include_directories(${PROJECT_NAME} PUBLIC ${EXT_INCLUDE})
target_link_libraries(${PROJECT_NAME} glfw ${GLFW_LIBRARIES})

