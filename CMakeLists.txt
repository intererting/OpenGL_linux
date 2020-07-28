cmake_minimum_required(VERSION 3.15)
project(OpenGL_linux)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_C_FLAGS "-ldl")

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/glfw/include)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/glad/include)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/glm)

find_library(OpenGL libGL.so /usr/lib)

add_library(GLAD SHARED ${PROJECT_SOURCE_DIR}/glad/glad.c)

add_executable(OpenGL_linux opengl/basic_3d.cpp)

target_link_libraries(OpenGL_linux ${PROJECT_SOURCE_DIR}/glfw/libglfw.so.3 GLAD OpenGL)
