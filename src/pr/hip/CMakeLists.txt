cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(pr_hip main.cc pr_hip_benchmark.cu pr_hip_benchmark.h)
    target_include_directories(pr_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(pr_hip pr time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)
