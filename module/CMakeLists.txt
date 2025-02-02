
# Get all .cpp and .c files in the source folder
file(GLOB SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/source/*.c
)

# Python Module
pybind11_add_module(KodoModule ${SOURCE_FILES})

# Link against the KodoEngine interface target
target_link_libraries(KodoModule PRIVATE KodoEngine)
