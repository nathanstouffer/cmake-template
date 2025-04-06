enable_testing()

# POPULATE: the cpp files in a variable stored as the name of the project
# set(_TEST_FILES
#     "${CMAKE_CURRENT_SOURCE_DIR}/cpp/"
# )

add_executable(tests ${_TEST_FILES})

# add directory structure to IDEs
source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}/" FILES ${_TEST_FILES})

target_include_directories(tests PRIVATE "include/private")

target_link_libraries(tests PRIVATE GTest::gtest_main)

# set up cpp files with precompiled headers
target_precompile_headers(tests PRIVATE <vector> <gtest/gtest.h>)

include(GoogleTest)
# finds all the tests associated with the executable
gtest_discover_tests(tests)