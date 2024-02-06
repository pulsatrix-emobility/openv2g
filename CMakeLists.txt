

# Collect all source files recursively
file(GLOB_RECURSE LIBRARY_SOURCE_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)

# Collect all header files recursively
file(GLOB LIBRARY_HEADER_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src/
        ${CMAKE_CURRENT_SOURCE_DIR}/src/appHandshake
        ${CMAKE_CURRENT_SOURCE_DIR}/src/codec
        ${CMAKE_CURRENT_SOURCE_DIR}/src/din
        ${CMAKE_CURRENT_SOURCE_DIR}/src/iso1
        ${CMAKE_CURRENT_SOURCE_DIR}/src/iso2
        ${CMAKE_CURRENT_SOURCE_DIR}/src/transport
        ${CMAKE_CURRENT_SOURCE_DIR}/src/xmldsig
        )


idf_component_register(
        SRCS
        ${LIBRARY_SOURCE_FILES}
        INCLUDE_DIRS
        ${LIBRARY_HEADER_DIR}

)

