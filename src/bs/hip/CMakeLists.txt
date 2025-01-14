cmake_minimum_required(VERSION 3.2)

if (HMARK_BUILD_HIP)
    # Prepare HIP (bs includes hip_runtime.h in bs_hip_benchmark.h)
    add_definitions(-D__HIP_PLATFORM_HCC__)
    set(HIP_ROOT /opt/rocm)
    include_directories(${HIP_ROOT}/include)
    set(HIP_LIBRARIES ${HIP_ROOT}/lib/libamdhip64.so)

    # Silence warnings of unused results
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-unused-result")

    HIP_ADD_EXECUTABLE(bs_hip main.cc bs_hip_benchmark.cu bs_hip_benchmark.h)
    target_include_directories(bs_hip PUBLIC ${CMAKE_SOURCE_DIR})
    target_link_libraries(bs_hip bs time_measurement command_line_option benchmark ${HIP_LIBRARIES})
endif (HMARK_BUILD_HIP)



