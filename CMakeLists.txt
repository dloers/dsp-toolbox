cmake_minimum_required(VERSION 3.14)

project(
    dsp-toolbox 
    VERSION 0.0.0
    DESCRIPTION "A generic C Digital Signal Processing library" 
    LANGUAGES C
)

option(BUILD_SHARED_LIBS 
    "Build dsp-toolbox as a shared library" OFF
)

option(DSP_TOOLBOX_BUILD_EXAMPLES 
    "Build the example executable" OFF
)

add_subdirectory(src)

if(DSP_TOOLBOX_BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()