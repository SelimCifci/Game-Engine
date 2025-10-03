cmake_minimum_required(VERSION 4.1.2)
project(GameEngine VERSION 0.0.0 LANGUAGES C)

set(CMAKE_C_STANDARD 23)

# Source files
set(SOURCES
    src/main.c    
)

add_executable(GameEngine ${SOURCES})

target_include_directories(GameEngine PRIVATE
    src
)

# SDL3
find_package(SDL3 REQUIRED CONFIG)
target_link_libraries(GameEngine PRIVATE SDL3::SDL3)

# OpenGL
find_package(OpenGL REQUIRED)
target_link_libraries(GameEngine PRIVATE OpenGL::GL)