cmake_minimum_required(VERSION 2.8)
project(exupstream1)

################################
# Metadata
################################

set(EXUPSTREAM1_VERSION "0.0.1")

################################
# Locate source
################################

file(GLOB_RECURSE INCLUDES include/*.h)
file(GLOB_RECURSE SRC src/*.cpp)

include_directories(include)

################################
# Build targets
################################

add_library(exupstream1 SHARED
    ${SRC}
    ${INCLUDES})

################################
# Export library
################################

export_project(
    NAME exupstream1
    INCLUDES ${CMAKE_CURRENT_LIST_DIR}/include
    LIBS exupstream1
    VERSION ${EXUPSTREAM1_VERSION}
)

