project(openv2gLibrary)

# Collect all source files recursively
file(GLOB_RECURSE LIBRARY_SOURCE_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)

# Collect all header files recursively
file(GLOB_RECURSE LIBRARY_HEADER_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/*.h)

# Add the library target
add_library(openv2gLibrary ${LIBRARY_SOURCE_FILES} ${LIBRARY_HEADER_FILES} )


# Include the directories to ensure we dont need to add a relative path where the headers of these folders will be used
# in the project that depends on this library
target_include_directories(openv2gLibrary PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/src/appHandshake
        ${CMAKE_CURRENT_SOURCE_DIR}/src/codec
        ${CMAKE_CURRENT_SOURCE_DIR}/src/din
        ${CMAKE_CURRENT_SOURCE_DIR}/src/iso1
        ${CMAKE_CURRENT_SOURCE_DIR}/src/iso2
        ${CMAKE_CURRENT_SOURCE_DIR}/src/transport
        ${CMAKE_CURRENT_SOURCE_DIR}/src/xmldsig
        )



