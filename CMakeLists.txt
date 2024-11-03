cmake_minimum_required(VERSION 3.10)

# Set the project name
project(spz)

# Set the C++ standard as C++17
set(CMAKE_CXX_STANDARD 17)

# Add libz as dependency
find_package(ZLIB REQUIRED)

# Add the source files
file(GLOB_RECURSE SOURCES "src/cc/*.cc")

# Include the headers
include_directories("src/cc")

# Create the library
add_library(spz SHARED ${SOURCES})
target_link_libraries(spz ZLIB::ZLIB)
