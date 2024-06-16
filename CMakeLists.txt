cmake_minimum_required(VERSION 3.20)

project(
  hkutils
  VERSION 0.1.0
  DESCRIPTION "A header only library with convenient utilities."
  LANGUAGES CXX
)

option(BUILD_TESTS    "build unit tests?" OFF)
option(BUILD_EXAMPLES "build examples?"   OFF)

set(HK_LIBRARY    utils)
set(HK_NAMESPACE  hk)

add_library(${PROJECT_NAME} INTERFACE)
add_library(${HK_NAMESPACE}::${HK_LIBRARY} ALIAS ${PROJECT_NAME})

target_include_directories(
  ${PROJECT_NAME}
  INTERFACE
  ${CMAKE_CURRENT_SOURCE_DIR}/include
)
