cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(aes_hip main.cc aes_hip_benchmark.cu aes_hip_benchmark.h)
    target_include_directories(aes_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(aes_hip aes time_measurement command_line_option benchmark)
endif (HMARK_BUILD_HIP)


