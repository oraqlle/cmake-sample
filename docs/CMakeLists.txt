set(DOXYGEN_EXTRACT_ALL YES)
set(DOXYGEN_BUILTIN_STL_SUPPORT YES)

file(GLOB HEADER_LIST CONFIGURE_DEPENDS "${CMakeSample_SOURCE_DIR}/include/**/*.hxx")

doxygen_add_docs(
    docs
    ALL
    ${HEADER_LIST}
    "${CMAKE_CURRENT_SOURCE_DIR}/mainpage.md"
    WORKING_DIRECTORY
    "${PROJECT_SOURCE_DIR}/include"
)
