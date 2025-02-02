# Get all .cpp and .c files in the source folder
file(GLOB SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.c
)

# Animation Module
add_library(anim STATIC ${SOURCE_FILES})

# Include Directories
target_include_directories(anim PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)
