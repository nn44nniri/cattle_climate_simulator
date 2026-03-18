cmake_minimum_required(VERSION 3.16)
project(cattle_climate_cpp VERSION 0.2.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_library(cattle_climate
    src/formulas.cpp
    src/settings.cpp
    src/simulator.cpp
)

target_include_directories(cattle_climate
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

add_executable(cattle_climate_example src/main.cpp)
target_link_libraries(cattle_climate_example PRIVATE cattle_climate)
