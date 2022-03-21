cmake_minimum_required(VERSION 3.14)

set(CMAKE_CXX_STANDARD 11)

project(main)

include(FetchContent)
FetchContent_Declare(
  googletest
  # Specify the commit you depend on and update it regularly.
  URL https://github.com/google/googletest/archive/e2239ee6043f73722e7aa812a459f54a28552929.zip
)

add_executable(main src/main.cpp)

install(TARGETS main)

# Test infrastructure
enable_testing()

add_executable(
  hello_test
  hello_test.cc
)
target_link_libraries(
  hello_test
  gtest_main
)

add_test(NAME example_test COMMAND hello_test)