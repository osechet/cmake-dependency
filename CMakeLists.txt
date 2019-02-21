project(helloworld)
cmake_minimum_required(VERSION 2.8.12)

include(CMakeFindDependencyMacro)
find_dependency(GTest)

message(STATUS "GTEST_FOUND = ${GTEST_FOUND}")
message(STATUS "GTest_FOUND = ${GTest_FOUND}")

add_executable(helloworld main.cpp)

target_include_directories(helloworld
    PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}
)

target_link_libraries(helloworld
    PUBLIC
)
