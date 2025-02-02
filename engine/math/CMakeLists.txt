# Get all .cpp and .c files in the source folder
file(GLOB SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.c
)

# Math Module
add_library(math STATIC ${SOURCE_FILES})

# Include Directories
target_include_directories(math PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)
