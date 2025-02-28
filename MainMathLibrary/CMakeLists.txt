# MainMathLibrary console application
project(MathLibrary)

# Set the source files
set(SOURCES
    MainMathLibrary.cpp
)

# Create the executable
add_executable(MainMathLibrary ${SOURCES})

# Link the MathLibrary DLL
target_link_libraries(MainMathLibrary PRIVATE MathLibrary)

# Set the output directory for the executable
set_target_properties(MainMathLibrary PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin
)

# Include the MathLibrary directory for header files
target_include_directories(MainMathLibrary PRIVATE ${CMAKE_SOURCE_DIR}/MathLibrary)