cmake_minimum_required(VERSION 3.11)
project(lab_1)

# Require modern C++
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#### Setup Directories ####
#Main output directory
set(OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin/")
# Ouput all DLLs from all libs into main build folder
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${OUTPUT_DIRECTORY})

#### Add External Dependencies ####
add_subdirectory("lib/SFML")
set(SFML_INCS "${CMAKE_SOURCE_DIR}/lib/SFML/include")

#### Practical 1 ####
add_executable(lab_1 main.cpp)
target_include_directories(lab_1 PRIVATE ${SFML_INCS})
target_link_libraries(lab_1 sfml-graphics sfml-window sfml-system)