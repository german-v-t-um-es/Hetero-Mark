cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(fir_hip main.cc fir_hip_benchmark.cu fir_hip_benchmark.h)
    target_include_directories(fir_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(fir_hip fir time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)
