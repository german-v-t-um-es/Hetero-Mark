cmake_minimum_required(VERSION 3.2)
if (${HMARK_BUILD_HIP})
    add_executable(kmeans_hip main.hip kmeans_hip_benchmark.hip kmeans_hip_benchmark.h)
    target_include_directories(kmeans_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(kmeans_hip PUBLIC kmeans time_measurement command_line_option
            benchmark hip::host hip::device)
endif ()

if (${HMARK_BUILD_HIP_NVIDIA})
    add_executable(kmeans_hip main.hip kmeans_hip_benchmark.hip kmeans_hip_benchmark.h)
    target_include_directories(kmeans_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(kmeans_hip PUBLIC kmeans time_measurement command_line_option
            benchmark)
endif ()
