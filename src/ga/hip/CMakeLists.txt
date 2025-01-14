cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(ga_hip main.cc ga_hip_benchmark.cu ga_hip_benchmark.h)
    target_include_directories(ga_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(ga_hip ga time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)
