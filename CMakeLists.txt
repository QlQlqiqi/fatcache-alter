cmake_minimum_required(VERSION 3.10)

# 设置项目名
project(fatcache)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)   # For clang-tidy.
set(BUILD_SHARED_LIBS OFF)              # We expect external libraries to be linked statically.
# set(CMAKE_CXX_STANDARD 17)              # Compile as C++17.
# set(CMAKE_CXX_STANDARD_REQUIRED ON)     # Require C++17 support.
set(CMAKE_BUILD_TYPE "Debug")
SET(ROOT_DIR ${CMAKE_SOURCE_DIR})
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O0 -g -Wall -ggdb")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99")  #设置c的编译选项
# set(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -Wall -g -ggdb")
# set(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")
# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -Wall -Wextra -Werror")
# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -Wno-unused-parameter -Wno-attributes") #TODO: remove
# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -O0 -ggdb -fno-omit-frame-pointer -fno-optimize-sibling-calls")
set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# include_directories(${ROOT_DIR}/src)
# include_directories(${ROOT_DIR}/test)
# include_directories(${ROOT_DIR}/src/include)
# include_directories(${ROOT_DIR}/third_party)
# include_directories(${ROOT_DIR}/third_party/sql_parser)
# include_directories(${ROOT_DIR}/third_party/base64)
# include_directories(${ROOT_DIR}/third_party/hiredis)
# include_directories(${ROOT_DIR}/third_party/r_star_tree)
# include_directories(${ROOT_DIR}/third_party/benchmark)
# include_directories(${ROOT_DIR}/third_party/gperftools)
include_directories(${ROOT_DIR}/src)

# LINK_DIRECTORIES(${ROOT_DIR}/src)
# LINK_DIRECTORIES(${ROOT_DIR}/test)
# LINK_DIRECTORIES(${ROOT_DIR}/src/include)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party/sql_parser)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party/base64)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party/hiredis)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party/r_star_tree)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party/benchmark)
# LINK_DIRECTORIES(${ROOT_DIR}/third_party/gperftools)
LINK_DIRECTORIES(${ROOT_DIR}/src)

# add_subdirectory(src)
# add_subdirectory(test)
# add_subdirectory(third_party)
# add_subdirectory(src_test)
add_subdirectory(src)