cmake_minimum_required(VERSION 3.24)
project(igraphicmodule)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Dependencies
list(PREPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

find_package(imodule REQUIRED)
find_package(igraphic REQUIRED)

set(SOURCE_FILES sources/no_source.cpp)

add_library(${PROJECT_NAME} SHARED ${SOURCE_FILES})

target_include_directories(${PROJECT_NAME} PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/includes
)

target_link_libraries(${PROJECT_NAME} PUBLIC imodule igraphic)