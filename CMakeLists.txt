cmake_minimum_required(VERSION 3.11)
set( CMAKE_CXX_COMPILER "/msys64/ucrt64/bin/g++.exe" )
set( CMAKE_C_COMPILER "/msys64/ucrt64/bin/gcc.exe" )
project(sample_cpp_project)

add_executable(main main.cpp my_add.cpp)

