include(FetchContent)

FetchContent_Declare(
    unity
    GIT_REPOSITORY https://github.com/ThrowTheSwitch/Unity.git
    GIT_TAG v2.7.0
    GIT_SHALLOW TRUE
)

FetchContent_MakeAvailable(unity)

set(DSP_TOOLBOX_TEST_SRCS
    ${CMAKE_CURRENT_SOURCE_DIR}/test_sine_generator.c
)

function(dsp_toolbox_compile_tests TEST_NAME TEST_FILE)
    
    add_executable(${TEST_NAME}
        ${TEST_FILE}
    )

    target_link_libraries(${TEST_NAME}
        PRIVATE
            dsp-toolbox::dsp-toolbox
            unity::framework
    )

    add_test(
        NAME ${TEST_NAME}
        COMMAND $<TARGET_FILE:${TEST_NAME}>
    )

endfunction()

foreach(FILE ${DSP_TOOLBOX_TEST_SRCS})

    get_filename_component(TEST_NAME ${FILE} NAME_WE)
    dsp_toolbox_compile_tests(${TEST_NAME} ${FILE})

endforeach()