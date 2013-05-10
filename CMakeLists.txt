cmake_minimum_required(VERSION 2.8)
project(evermind)
 
set(EVERMIND_DIR "${CMAKE_SOURCE_DIR}/evermind")
set(EVERMIND_SOURCE_DIR "${EVERMIND_DIR}")
set(EVERMIND_INCLUDE_DIR "${EVERMIND_DIR}")
file(GLOB_RECURSE EVERMIND_SOURCES_CXX "${EVERMIND_SOURCE_DIR}/*.cpp")

list( APPEND CMAKE_CXX_FLAGS "-std=c++11 ${CMAKE_CXX_FLAGS} -Wall -Werror")

include_directories(${EVERMIND_INCLUDE_DIR})

find_package(Boost 1.49 COMPONENTS program_options REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

add_executable(evermind ${EVERMIND_SOURCES_CXX})
target_link_libraries(evermind ${Boost_LIBRARIES})
