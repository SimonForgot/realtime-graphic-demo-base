#EXT_INCLUDE is all the include files that external items offer
set(EXT_INCLUDE ext/glad/include
                ext/imgui/include
    CACHE STRING INTERNAL FORCE)

#GLAD_SRC is used for glad.c
set(GLAD_SRC ${CMAKE_CURRENT_SOURCE_DIR}/glad/src CACHE STRING INTERNAL FORCE)
set(IMGUI_SRC ${CMAKE_CURRENT_SOURCE_DIR}/imgui/src CACHE STRING INTERNAL FORCE)

