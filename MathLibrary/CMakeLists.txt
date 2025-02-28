# MathLibrary DLL project
project(MathLibrary)

# Set the source files
set(SOURCES
    MathLibrary.cpp
    MathLibrary.h
)

# Create the DLL
add_library(MathLibrary SHARED ${SOURCES})

# Export symbols for the DLL
target_compile_definitions(MathLibrary PRIVATE MATHLIBRARY_EXPORTS)

# Set the output directory for the DLL
set_target_properties(MathLibrary PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin
    LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin
    ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib
)

# Include the current directory for header files
target_include_directories(MathLibrary PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})