cmake_minimum_required(VERSION 3.19)


set(PRJNAME testglfwd3d)
project(${PRJNAME})


set(ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../..)
set(GENERATION_ROOT ${CMAKE_CURRENT_BINARY_DIR})


# ==================================================================================================
# Test apps
# ==================================================================================================


### src

file(GLOB src "./*.cpp" "./*.h" "./*.hpp")

### inc

include_directories(${GENERATION_ROOT})
include_directories(./)

### exe

add_executable(${PRJNAME} ${src})

### link

target_link_libraries(${PRJNAME} PUBLIC glm)
target_link_libraries(${PRJNAME} PUBLIC glfw)
# target_link_libraries(${PRJNAME} PUBLIC glad)

### compiler

target_compile_options(${PRJNAME} PRIVATE ${COMPILER_FLAGS})
set_target_properties(${PRJNAME} PROPERTIES FOLDER Samples)
