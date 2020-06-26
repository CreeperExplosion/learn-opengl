
file(
    GLOB CPP_FILE src/core_renderer/*.cpp
    GLOB CPP_FILE vendor/glad/src/*.c
    
    )
file(
    GLOB H_FILE src/core_renderer/*.h
    # GLOB H_FILE src/*.h
    
    )

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(
    vendor/GLFW
)


add_library(
    graphics
    STATIC
    "${H_FILE}"
    "${CPP_FILE}"
)

target_link_libraries(
    graphics
    glfw
)

target_include_directories(
    graphics
    PRIVATE
    vendor/glad/include
    vendor/GLFW/include
)


target_include_directories(
    graphics
    PUBLIC
    src/
)
