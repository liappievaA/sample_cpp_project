cmake_minimum_required(VERSION 3.11)
# set( CMAKE_CXX_COMPILER "/msys64/ucrt64/bin/g++.exe" )
# set( CMAKE_C_COMPILER "/msys64/ucrt64/bin/gcc.exe" )
project(sample_cpp_project)
# add_subdirectory(googletest)
include_directories(include)
add_executable(main main.cpp src/my_add.cpp)

include (FetchContent)
FetchContent_Declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG v1.15.2
)
FetchContent_MakeAvailable(googletest)

enable_testing()
add_executable(tests test_add.cpp src/my_add.cpp)
target_link_libraries(tests gtest gtest_main)

include(GoogleTest)
gtest_discover_tests(tests)
