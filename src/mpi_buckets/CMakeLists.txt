cmake_minimum_required(VERSION 3.1)
project(mpi_buckets)

set(CMAKE_CXX_FLAGS "-std=c++11 -O3")
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
find_package(MPI REQUIRED)

include_directories(${MPI_INCLUDE_PATH})
include_directories(src)
include_directories(dist_hash)
include_directories(mock)

file(GLOB TESTS "tests/*.cpp")

add_executable(test_mpi_buckets ${TESTS})
target_link_libraries(test_mpi_buckets ${MPI_LIBRARIES})
