cmake_minimum_required(VERSION 3.14)

project(main)

add_executable(main src/main.cpp)

install(TARGETS main)

enable_testing()
add_test(NAME main COMMAND main)
