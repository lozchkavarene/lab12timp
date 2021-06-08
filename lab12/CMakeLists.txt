cmake_minimum_required(VERSION 3.12)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/cpp-pm/hunter/archive/v0.23.300.tar.gz"
    SHA1 "0b568c54acf357a51fda029cde97271ec20a87f4"
)

project(print)

hunter_add_package(GTest)
find_package(GTest CONFIG REQUIRED)

include_directories(lib)
add_library(print STATIC lib/print.cpp)

option(BUILD_TESTS "Build tests" OFF)

if(BUILD_TESTS)

  enable_testing()
  file(GLOB PRINT_TEST_SOURCES tests/*.cpp)
  add_executable(check ${PRINT_TEST_SOURCES})
  target_link_libraries(check PUBLIC print GTest::main)
  add_test(NAME check COMMAND check)

endif()

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/demo/main.cpp)
target_link_libraries(demo print)
install(TARGETS demo RUNTIME DESTINATION bin)
