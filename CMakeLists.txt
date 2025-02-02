# CMake Version
cmake_minimum_required(VERSION 3.15)

# Main Build Project
project(KodoEngine)

# C++ Version
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Directories for {Static | Shared | Executable}
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}")

# Add External Dependencies
add_subdirectory(external)

# Add Internal Modules
add_subdirectory(engine/anim)
add_subdirectory(engine/entity)
add_subdirectory(engine/gui)
add_subdirectory(engine/math)
add_subdirectory(engine/render)
add_subdirectory(engine/scene)

# Define an interface target for KodoEngine
add_library(KodoEngine INTERFACE)

# Link libraries to the interface target
target_link_libraries(KodoEngine INTERFACE
    glad
    glfw
    imgui
)

# Include directories for the interface target
target_include_directories(KodoEngine INTERFACE
    # External Dependencies
    ${CMAKE_SOURCE_DIR}/external/GLM
    # Internal Modules
    ${CMAKE_SOURCE_DIR}/engine/anim/include
    ${CMAKE_SOURCE_DIR}/engine/entity/include
    ${CMAKE_SOURCE_DIR}/engine/gui/include
    ${CMAKE_SOURCE_DIR}/engine/math/include
    ${CMAKE_SOURCE_DIR}/engine/render/include
    ${CMAKE_SOURCE_DIR}/engine/scene/include
)

# Add Main Application
add_subdirectory(app)

# Add Python Module
add_subdirectory(python)