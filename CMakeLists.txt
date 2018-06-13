cmake_minimum_required(VERSION 3.10)
project(DelaunayTriangulation3D)

set(CMAKE_CXX_STANDARD 11)

find_package(CGAL QUIET)

include( ${CGAL_USE_FILE} )

include( CGAL_CreateSingleSourceCGALProgram )

create_single_source_cgal_program("main.cpp")

set(SOURCE_FILES glad.c main.cpp glad.c shader.h)

add_executable(DelaunayTriangulation3D ${SOURCE_FILES})
target_link_libraries(DelaunayTriangulation3D CGAL GL GLU glfw3 X11 Xrandr pthread Xi dl Xinerama)