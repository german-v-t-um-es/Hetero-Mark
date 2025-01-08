if (${HMARK_BUILD_HIP})
    add_executable(hist_hip main.hip hist_hip_benchmark.hip hist_hip_benchmark.h)
    target_include_directories(hist_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(hist_hip PUBLIC hist time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(hist_hip main.hip hist_hip_benchmark.hip hist_hip_benchmark.h)
    target_include_directories(hist_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(hist_hip PUBLIC hist time_measurement command_line_option
            benchmark)
endif ()

