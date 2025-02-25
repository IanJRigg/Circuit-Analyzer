cmake_minimum_required(VERSION 3.12)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake_modules/")

set(SRC_DIR ${CMAKE_SOURCE_DIR}/src/)
set(TEST_DIR ${CMAKE_SOURCE_DIR}/test/)
set(INCLUDE_DIR ${CMAKE_SOURCE_DIR}/include/)

set(PROJECT_NAME circlyzer)
set(PROJECT_VERSION 1.0.0)

project(
    ${PROJECT_NAME} 
    VERSION ${PROJECT_VERSION}
    LANGUAGES CXX
)

set(LIBRARY_NAME circlyzer)
set(TEST_SUITE_NAME circlyzer_test)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)


add_subdirectory(src)

enable_testing()
add_subdirectory(test)