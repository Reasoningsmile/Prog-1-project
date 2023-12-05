cmake_minimum_required(VERSION 3.26)
project(SFML_Space_Invaders)

include_directories(c:/SFML/include)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake_modules")
find_package(SFML REQUIRED system window graphics)
add_executable(SFML_Space_Invaders main.cpp)

if (SFML_FOUND)
    include_directories(${CMAKE_CURRENT_LIST_DIR})
    target_link_libraries(SFML_Space_Invaders ${SFML_LIBRARIES})
endif()

if(WIN32)
    file(GLOB BINARY_DEP_DLLS "${SFML_INCLUDE_DIR}/../BIN/*.DLL")
    FILE(COPY ${BINARY_DEP_DLLS} DESTINATION ${CMAKE_BINARY_DIR})
endif()