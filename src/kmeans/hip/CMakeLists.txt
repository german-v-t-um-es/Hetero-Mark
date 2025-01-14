cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(kmeans_hip main.cc kmeans_hip_benchmark.cu kmeans_hip_benchmark.h)
    target_include_directories(kmeans_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(kmeans_hip kmeans time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)
