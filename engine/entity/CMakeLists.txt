# Get all .cpp and .c files in the source folder
file(GLOB SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.c
)

# Entity Module
add_library(entity STATIC ${SOURCE_FILES})

# Include Directories
target_include_directories(entity PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)
