cmake_minimum_required(VERSION 3.17)
project(OpenGl)
set(CMAKE_CXX_STANDARD 17)

add_subdirectory(Dependencies/glfw-3.3.4/)
include_directories(Dependencies/glfw-3.3.4/include)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
include_directories(${GLEW_INCLUDE_DIRS})
link_libraries(${GLEW_LIBRARIES})

add_executable(OpenGl main.cpp)
target_link_libraries(OpenGl glfw ${GLFW_LIBRARIES})
target_link_libraries(OpenGl glfw ${OPENGL_LIBRARIES} ${GLFW_LIBRARIES})