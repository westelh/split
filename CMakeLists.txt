cmake_minimum_required(VERSION 3.9)
project(SPLIT LANGUAGES CXX)

if("${PROJECT_SOURCE_DIR}" STREQUAL "${PROJECT_BINARY_DIR}")
	message(SEND_ERROR "In-source builds are not allowed.")
endif("${PROJECT_SOURCE_DIR}" STREQUAL "${PROJECT_BINARY_DIR}")

set(ENABLE_TEST ON)

if(ENABLE_TEST)
	enable_testing()
	add_subdirectory(${CMAKE_SOURCE_DIR}/googletest)
	add_executable(test_exec test.cpp)
	target_link_libraries(test_exec gtest_main)
	add_test(test_all test_exec)
endif()
