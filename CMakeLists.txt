cmake_minimum_required(VERSION 3.20)

project(euler VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_library(euler STATIC
    src/Vec2.cpp
    src/Vec3.cpp
    src/Vec4.cpp
    src/Functions.cpp
)

target_include_directories(euler
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

add_executable(example
    examples/main.cpp
)

target_link_libraries(example
    PRIVATE
        euler
)