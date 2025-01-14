cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(hist_hip main.cc hist_hip_benchmark.cu hist_hip_benchmark.h)
    target_include_directories(hist_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(hist_hip hist time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)

