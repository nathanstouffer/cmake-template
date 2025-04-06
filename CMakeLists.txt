cmake_minimum_required(VERSION 3.24)

# POPULATE: project name
project(project-name LANGUAGES CXX)

# POPULATE: CXX version
# set(CMAKE_CXX_STANDARD 17)
# set(CXX_STANDARD_REQUIRED ON)

# set property so Visual Studio generates filters corresponding to folders
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

if (${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_CURRENT_SOURCE_DIR})
    set(BUILD_TESTS TRUE)
    enable_testing()
    set(BUILD_DOCS TRUE)
endif()

add_subdirectory(code)