cmake_minimum_required(VERSION 2.8.4)
project(freebase_backend)
set(VERSION_MAJOR 1)
set(VERSION_MINOR 0)
set(VERSION_PATCH 0)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/modules/")
include_directories("${CMAKE_INSTALL_PREFIX}/include")

ADD_DEFINITIONS(
    -std=c++11 # Or -std=c++0x
    # Other flags
    -DBOOST_LOG_DYN_LINK
)

find_package (Threads)
find_package (CPPCMS REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_executable(freebase_backend main.cpp SourcesToolBackend.cpp)

target_link_libraries(freebase_backend ${CMAKE_THREAD_LIBS_INIT} ${LIBCPPCMS_LIBRARY} )