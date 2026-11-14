set(DSP_TOOLBOX_EXAMPLES_SRCS
    ${CMAKE_CURRENT_SOURCE_DIR}/sine_generator.c
    ${CMAKE_CURRENT_SOURCE_DIR}/sine_sweep.c
)

function(dsp_toolbox_compile_examples EAXMPLE_NAME EXAMPLE_FILE)
    
    add_executable(${EAXMPLE_NAME}
        ${EXAMPLE_FILE}
    )

    target_link_libraries(${EAXMPLE_NAME}
        PRIVATE
            dsp-toolbox::dsp-toolbox
    )

endfunction()

foreach(FILE ${DSP_TOOLBOX_EXAMPLES_SRCS})

    get_filename_component(EXAMPLE_NAME ${FILE} NAME_WE)
    dsp_toolbox_compile_examples(${EXAMPLE_NAME} ${FILE})

endforeach()