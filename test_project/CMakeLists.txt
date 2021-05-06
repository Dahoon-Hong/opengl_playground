cmake_minimum_required(VERSION 3.7)
project(test_project)
set(OUTPUT run)

set(GLUT_ROOT_PATH "../opengl/freeglut")

find_package(GLUT REQUIRED)
#find_package(GL REQUIRED)
find_package(OpenGL REQUIRED)
find_library(GLUT_glut_LIBRARY NAMES glut freeglut opengl glu 
    PATHS
    ${GLUT_ROOT_PATH}/lib
    ${GLUT_ROOT_PATH}/bin
)
INCLUDE_DIRECTORIES("../opengl/freeglut/include")
LINK_DIRECTORIES(${GLUT_ROOT_PATH}/res)



set(CMAKE_CXX_COMPILER g++)
set(SOURCES src/main.cpp)

add_executable(${OUTPUT} ${SOURCES})
target_link_libraries(${OUTPUT} ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES})

set(EXECUTABLE_OUTPUT_PATH "bin")