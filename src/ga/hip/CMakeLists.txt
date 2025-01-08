if (${HMARK_BUILD_HIP})
    add_executable(ga_hip main.hip ga_hip_benchmark.hip ga_hip_benchmark.h)
    target_include_directories(ga_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(ga_hip PUBLIC ga time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(ga_hip main.hip ga_hip_benchmark.hip ga_hip_benchmark.h)
    target_include_directories(ga_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(ga_hip PUBLIC ga time_measurement command_line_option
            benchmark)
endif ()
