
# -------------------- GLAD -------------------- #
add_subdirectory(glad)

# -------------------- GLFW -------------------- #
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)
set(BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)
add_subdirectory(glfw)

# -------------------- GLM -------------------- #
set(GLM_ENABLE_CXX_17 ON CACHE BOOL "" FORCE)
add_subdirectory(glm)

# -------------------- IMGUI -------------------- #
set(IMGUI_DIR ${CMAKE_CURRENT_SOURCE_DIR}/ImGui)
set(IMGUI_SRC
    "${IMGUI_DIR}/imgui.cpp"
    "${IMGUI_DIR}/imgui_demo.cpp"
    "${IMGUI_DIR}/imgui_draw.cpp"
    "${IMGUI_DIR}/imgui_tables.cpp"
    "${IMGUI_DIR}/imgui_widgets.cpp"
    "${IMGUI_DIR}/backends/imgui_impl_glfw.cpp"
    "${IMGUI_DIR}/backends/imgui_impl_opengl3.cpp"
)
add_library(imgui STATIC ${IMGUI_SRC})
target_include_directories(imgui PUBLIC
    "${IMGUI_DIR}"
    "${IMGUI_DIR}/backends"
)
target_link_libraries(imgui PUBLIC glad glfw)

# -------------------- PYBIND11 -------------------- #
add_subdirectory(pybind11)
