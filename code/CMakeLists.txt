list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

if (MSVC AND CMAKE_GENERATOR MATCHES "Ninja")
  # Avoid C1041 when compiling in parallel: don't use a shared compile PDB.
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<$<CONFIG:Debug,RelWithDebInfo>:Embedded>")
endif()

if (BUILD_TESTS)
    include(CTest)
    include(CoverageBuildType)
endif()

add_subdirectory(deps)
add_subdirectory(src)

if (BUILD_TESTS)
    add_subdirectory(tests)
endif()

if (BUILD_DOCS)
    include(GenerateDocs)
endif()