cmake_minimum_required(VERSION 3.10)
project(OpenCLTest VERSION 1.0 LANGUAGES CXX)

find_package(OpenCL REQUIRED)

add_executable(test src/main.cc)
target_include_directories(test PUBLIC ${OpenCL_INCLUDE_DIRS})
target_link_libraries(test ${OpenCL_LIBRARIES})
target_compile_definitions(test PRIVATE CL_TARGET_OPENCL_VERSION=100)