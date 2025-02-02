# Get all .cpp and .c files in the source folder
file(GLOB SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.c
)

# Render Module
add_library(render STATIC ${SOURCE_FILES})

# Include Directories
target_include_directories(render PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)
