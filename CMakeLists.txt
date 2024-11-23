cmake_minimum_required(VERSION 3.29)
project(mincostpmatch)

set(CMAKE_CXX_STANDARD 14)

add_subdirectory(gmpwrap)

add_library(mincostpmatch SHARED BinaryHeap.cpp
        BinaryHeap.h
        Example.cpp
        Globals.h
        Graph.cpp
        Graph.h
        Matching.cpp
        Matching.h
        types.h library.h)

target_link_libraries(mincostpmatch gmpwrap)

add_executable(mincostpmatch_test Example.cpp BinaryHeap.h BinaryHeap.cpp Globals.h Graph.cpp Graph.h Matching.cpp Matching.h types.h library.h)
target_link_libraries(mincostpmatch_test gmpwrap)