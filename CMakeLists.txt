cmake_minimum_required(VERSION 3.0.2)

project (booringTime)
file(GLOB_RECURSE SOURCES
        "${CMAKE_CURRENT_SOURCE_DIR}/*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.xml"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.json"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.h")
list(SORT SOURCES)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(exercise ${SOURCES} )
set ( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wfatal-errors -Wall -pedantic -Wempty-body -Wno-deprecated -Wno-deprecated-declarations")
set (CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -lGL -lSDL2 -lSDL2_ttf -pthread" )
target_link_libraries(exercise stdc++fs)
