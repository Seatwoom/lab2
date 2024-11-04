#CMake
cmake_minimum_required(VERSION 3.29)

project(lab2)

set(CMAKE_CXX_STANDARD 20)

# Додаємо src/calculator.cpp
add_library(calculator STATIC src/calculator.cpp)

target_include_directories(calculator PUBLIC ${PROJECT_SOURCE_DIR}/include)

# Додаємо src/main.cpp
add_executable(lab2 src/main.cpp)

# Зв'язуємо "calculator" and main.cpp
target_link_libraries(lab2 calculator)

# Ninja
set(CMAKE_MAKE_PROGRAM "ninja")