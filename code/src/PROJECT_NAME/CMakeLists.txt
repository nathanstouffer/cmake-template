# POPULATE: the files for this project in a variable stored as the name of the project
set(_FILES
	"${CMAKE_CURRENT_SOURCE_DIR}/"
)

# add directory structure to IDEs
source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}/" FILES ${_FILES})