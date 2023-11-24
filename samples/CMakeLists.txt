cmake_minimum_required(VERSION 3.19)
project(feynman-samples C ASM)



set(ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/..)
set(GENERATION_ROOT ${CMAKE_CURRENT_BINARY_DIR})


# ==================================================================================================
# Compiler flags
# ==================================================================================================

if (MSVC)
    set(COMPILER_FLAGS )
else()
    set(COMPILER_FLAGS
            -Wno-extern-c-compat
            $<$<NOT:$<PLATFORM_ID:Linux>>:-Wno-address-of-packed-member>)
endif()

# ==================================================================================================
# Test apps
# ==================================================================================================

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/testd3d)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/testglfw)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/testglfwd3d)

