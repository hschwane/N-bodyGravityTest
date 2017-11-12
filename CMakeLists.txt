cmake_minimum_required(VERSION 3.6)
project(gravitySim)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake)

find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(GLFW3 REQUIRED)
find_package(GLM REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(SOURCE_FILES main.cpp ShaderTools.cpp)

include_directories(
        ${OPENGL_INCLUDE_DIRS}
        ${GLEW_INCLUDE_PATH}
        ${GLFW3_INCLUDE_PATH}
        ${GLM_INCLUDE_PATH}
)

add_executable(gravitySim ${SOURCE_FILES})
target_link_libraries(gravitySim
        ${GLFW3_LIBRARIES}
        ${GLEW_LIBRARIES}
        ${OPENGL_LIBRARY}
        )