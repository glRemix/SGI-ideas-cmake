cmake_minimum_required(VERSION 3.15)
project(ideas C)

set(CMAKE_C_STANDARD 99)

option(ENABLE_SHADOWS "Enable shadow rendering" OFF)
option(ENABLE_LETTER_OUTLINES "Enable letter outline rendering" OFF)

# Configure freeglut to build as static library
set(FREEGLUT_BUILD_STATIC_LIBS ON CACHE BOOL "" FORCE)
set(FREEGLUT_BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)
set(FREEGLUT_BUILD_DEMOS OFF CACHE BOOL "" FORCE)

# Add freeglut submodule
add_subdirectory(external/freeglut)

# Find OpenGL
find_package(OpenGL REQUIRED)

# Source files
set(SOURCES
    a.c
    b.c
    d.c
    draw_holder.c
    draw_lamp.c
    draw_logo.c
    draw_logo_line.c
    draw_logo_shadow.c
    e.c
    f.c
    h.c
    i.c
    m.c
    n.c
    o.c
    p.c
    r.c
    s.c
    t.c
    track.c
    w.c
)

# Create executable
add_executable(ideas ${SOURCES})

# Include directories
target_include_directories(ideas PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/external/freeglut/include
)

# Link libraries
target_link_libraries(ideas PRIVATE
    freeglut_static
    OpenGL::GL
    OpenGL::GLU
)

if(ENABLE_SHADOWS)
    target_compile_definitions(ideas PRIVATE ENABLE_SHADOWS)
endif()

if(ENABLE_LETTER_OUTLINES)
    target_compile_definitions(ideas PRIVATE ENABLE_LETTER_OUTLINES)
endif()

# Platform-specific settings
if(WIN32)
    # Windows-specific settings
    target_compile_definitions(ideas PRIVATE FREEGLUT_STATIC)
elseif(UNIX AND NOT APPLE)
    # Linux-specific settings
    target_link_libraries(ideas PRIVATE m Xmu Xext X11)
endif()
