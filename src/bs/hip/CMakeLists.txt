if (${HMARK_BUILD_HIP})
    add_executable(bs_hip main.hip bs_hip_benchmark.hip bs_hip_benchmark.h)
    target_include_directories(bs_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(bs_hip PUBLIC bs time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(bs_hip main.hip bs_hip_benchmark.hip bs_hip_benchmark.h)
    target_include_directories(bs_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(bs_hip PUBLIC bs time_measurement command_line_option
            benchmark)
endif ()
