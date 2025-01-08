if (${HMARK_BUILD_HIP})
    add_executable(pr_hip main.hip pr_hip_benchmark.hip pr_hip_benchmark.h)
    target_include_directories(pr_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(pr_hip PUBLIC pr time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(pr_hip main.hip pr_hip_benchmark.hip pr_hip_benchmark.h)
    target_include_directories(pr_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(pr_hip PUBLIC pr time_measurement command_line_option
            benchmark)
endif ()
