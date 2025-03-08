cmake_minimum_required(VERSION 3.30)

project(CLion_CMake_Juce_Template)

set(CMAKE_CXX_STANDARD 20)

set(LIB_DIR ${CMAKE_CURRENT_SOURCE_DIR}/libs)

include(cmake/cpm.cmake)

CPMAddPackage(
        NAME JUCE

        GITHUB_REPOSITORY juce-framework/JUCE
        GIT_TAG 8.0.6
        VERSION v8.0.6
        SOURCE_DIR ${JUCE_SOURCE_DIR}
)

add_subdirectory(Plugin)