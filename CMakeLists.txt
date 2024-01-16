cmake_minimum_required(VERSION 3.27.7)
project("flash" LANGUAGES CXX)

find_package(cli CONFIG REQUIRED)
find_package(libpqxx CONFIG REQUIRED)

file(GLOB_RECURSE SOURCES "${CMAKE_SOURCE_DIR}/src/*.cpp")

add_executable(main ${SOURCES})

target_include_directories(main PRIVATE "${CMAKE_SOURCE_DIR}/include/")

target_link_libraries(main PRIVATE cli::cli libpqxx::pqxx)
