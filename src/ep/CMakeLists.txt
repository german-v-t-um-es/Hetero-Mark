set(FOLDER_NAME ep)
set(SUBDIRECTORIES 
  cl12
  cuda
  hip
)
set(SRC_FILES
  ep_benchmark.cc
  ep_command_line_options.cc
)
set(HEADER_FILES
  ep_benchmark.h
  ep_command_line_options.h
)

find_package(OpenCV)

if (${OpenCV_FOUND})
  include_directories(${OpenCV_INCLUDE_DIRS})
  add_library(${FOLDER_NAME} ${SRC_FILES} ${HEADER_FILES})

  foreach(subdir ${SUBDIRECTORIES})
      add_subdirectory(${subdir})
  endforeach(subdir)

else ()
  message("OpenCV is not found, skipping the EP benchmark")
endif()
