cmake_minimum_required(VERSION 3.24)

# POPULATE: project name
project(project-name LANGUAGES CXX)

# POPULATE: CXX version
# set(CMAKE_CXX_STANDARD 17)
# set(CXX_STANDARD_REQUIRED ON)

# set property so Visual Studio generates filters corresponding to folders
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

add_subdirectory(code)