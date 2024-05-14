project(
  "rocksDBWrapper"
  VERSION 1.1.0
  DESCRIPTION "Header wrapper facilitating seamless integration of the RocksDB database into C++ projects."
  LANGUAGES CXX
)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS} -fPIC")
set(CMAKE_CXX_STANDARD 20)
include_directories(include)

file(GLOB_RECURSE SOURCES "src/*.cpp")

add_library(${PROJECT_NAME} SHARED ${SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC ${ROCKSDB_INCLUDE_DIR})
target_link_libraries(${PROJECT_NAME} PUBLIC rocksdb)
