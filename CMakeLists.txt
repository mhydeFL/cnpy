CMAKE_MINIMUM_REQUIRED(VERSION 3.0 FATAL_ERROR)
find_package(ZLIB REQUIRED)

add_library(cnpy-static STATIC
    cnpy.cpp
    cnpy.h
)
include_directories(${ZLIB_INCLUDE_DIRS})
target_link_libraries(cnpy-static ${ZLIB_LIBRARIES})
set_target_properties(cnpy-static PROPERTIES OUTPUT_NAME cnpy)
install(TARGETS cnpy-static ARCHIVE DESTINATION lib)
