cmake_minimum_required(VERSION 3.25 FATAL_ERROR)

project(
  "rocksDBWrapper"
  VERSION 1.0.0
  DESCRIPTION "Header wrapper facilitating seamless integration of the RocksDB database into C++ projects."
  LANGUAGES CXX
)

set(CMAKE_CXX_STANDARD 20)
include_directories(include)

file(GLOB_RECURSE SOURCES "src/*.cpp")

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/../external/rocksdb)
add_library(${PROJECT_NAME} SHARED ${SOURCES})

target_link_libraries(${PROJECT_NAME} PUBLIC rocksdb)
