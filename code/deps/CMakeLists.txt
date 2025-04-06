include(FetchContent)

if (BUILD_TESTS)
    # declare and populate googletest dependency
    FetchContent_Declare(
        googletest 
        GIT_REPOSITORY https://github.com/google/googletest.git
        GIT_TAG v1.14.0
    )
    FetchContent_MakeAvailable(googletest)
endif()