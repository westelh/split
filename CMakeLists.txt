cmake_minimum_required(VERSION 3.9)
project(SPLIT LANGUAGES CXX)

if("${PROJECT_SOURCE_DIR}" STREQUAL "${PROJECT_BINARY_DIR}")
	message(SEND_ERROR "In-source builds are not allowed.")
endif("${PROJECT_SOURCE_DIR}" STREQUAL "${PROJECT_BINARY_DIR}")

set(ENABLE_TEST ON)

if(ENABLE_TEST)
	find_package(GTest REQUIRED)
endif()
