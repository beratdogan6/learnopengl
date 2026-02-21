cmake_minimum_required(VERSION 3.15)
project(learnopengl C CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(app
  main.cpp
  src/glad.c
)

target_include_directories(app PRIVATE
  ${CMAKE_SOURCE_DIR}/include
)

# MSYS2 mingw64'te GLFW'nin config paketi çoğu zaman var:
find_package(glfw3 CONFIG QUIET)

if (glfw3_FOUND)
  target_link_libraries(app PRIVATE glfw)
else()
  # Alternatif: direkt isimle link (mingw64'te genelde çalışır)
  target_link_libraries(app PRIVATE glfw3)
endif()

# Windows OpenGL
target_link_libraries(app PRIVATE opengl32)
