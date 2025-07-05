cmake_minimum_required(VERSION 3.10)
project(LaserRoomSim)

set(CMAKE_CXX_STANDARD 17)

# Ruta de GLFW y GLAD
set(GLFW_ROOT "C:/Librerias/glfw")
set(GLAD_ROOT "C:/Librerias/glad")

# Incluir los headers de GLFW y GLAD
include_directories(${GLFW_ROOT}/include)
include_directories(${GLAD_ROOT}/include)


set(SOURCES
        main.cpp
        ${GLAD_ROOT}/src/glad.c
)

# Archivo de salida

# Crear la carpeta de salida y linkear las librerías
link_directories(${GLFW_ROOT}/lib-mingw-w64)

# Archivo de salida
add_executable(OpenGL_GLFW ${SOURCES})

# Linkear las librerías
target_link_libraries(OpenGL_GLFW
        glfw3
        opengl32
)

