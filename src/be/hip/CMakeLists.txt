cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    HIP_ADD_EXECUTABLE(be_hip main.cc be_hip_benchmark.cu be_hip_benchmark.h)
    target_include_directories(be_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(be_hip be time_measurement command_line_option benchmark ${OpenCV_LIBS})
endif (HMARK_BUILD_HIP)

