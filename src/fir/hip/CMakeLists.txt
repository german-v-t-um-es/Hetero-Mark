if (${HMARK_BUILD_HIP})
    add_executable(fir_hip main.hip fir_hip_benchmark.hip fir_hip_benchmark.h)
    target_include_directories(fir_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(fir_hip PUBLIC fir time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(fir_hip main.hip fir_hip_benchmark.hip fir_hip_benchmark.h)
    target_include_directories(fir_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(fir_hip PUBLIC fir time_measurement command_line_option
            benchmark)
endif ()
