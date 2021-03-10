cmake_minimum_required(VERSION 3.15)

project(linenoise)

# build liblinenoise
add_library(
    linenoise
    STATIC
        ${PROJECT_SOURCE_DIR}/src/ConvertUTF.cpp
        ${PROJECT_SOURCE_DIR}/src/linenoise.cpp
        ${PROJECT_SOURCE_DIR}/src/wcwidth.cpp
)

target_include_directories(linenoise PUBLIC ${PROJECT_SOURCE_DIR}/include)

if (CMAKE_CXX_COMPILER_ID STREQUAL "MSVC")
    target_compile_definitions(linenoise PRIVATE _CRT_SECURE_NO_WARNINGS=1)
endif()

add_subdirectory(tst)
