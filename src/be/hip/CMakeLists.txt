if (${HMARK_BUILD_HIP})
    add_executable(be main.hip be_hip_benchmark.hip be_hip_benchmark.h)
    target_include_directories(be_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(be_hip PUBLIC be time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(be_hip main.hip be_hip_benchmark.hip be_hip_benchmark.h)
    target_include_directories(be_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(be_hip PUBLIC be time_measurement command_line_option
            benchmark ${OpenCV_LIBS})
endif ()

