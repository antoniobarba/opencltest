cmake_minimum_required(VERSION 3.30)
project(OpenCLTest VERSION 1.0 LANGUAGES C CXX)

find_package(OpenCL REQUIRED)

add_executable(test src/main.cc)
add_executable(matvec src/matvec.c)

target_include_directories(test PUBLIC ${OpenCL_INCLUDE_DIRS})
target_link_libraries(test ${OpenCL_LIBRARIES})
target_compile_definitions(test PRIVATE CL_TARGET_OPENCL_VERSION=100)

target_include_directories(matvec PUBLIC ${OpenCL_INCLUDE_DIRS})
target_link_libraries(matvec ${OpenCL_LIBRARIES})
target_compile_definitions(matvec PRIVATE CL_TARGET_OPENCL_VERSION=100)
