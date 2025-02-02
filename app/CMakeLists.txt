# Get all .cpp and .c files in the source folder
file(GLOB SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.c
)

# Application
add_executable(KodoApp ${SOURCE_FILES})

# Link against the KodoEngine interface target
target_link_libraries(KodoApp PRIVATE KodoEngine)
