cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(ep_hip main.cc ep_hip_benchmark.cu ep_hip_benchmark.h)
    target_include_directories(ep_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(ep_hip ep time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)
