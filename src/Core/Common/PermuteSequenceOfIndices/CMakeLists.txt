cmake_minimum_required(VERSION 3.10.2)

project(PermuteSequenceOfIndices)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(PermuteSequenceOfIndices Code.cxx)
target_link_libraries(PermuteSequenceOfIndices ${ITK_LIBRARIES})

install(TARGETS PermuteSequenceOfIndices
  DESTINATION bin/ITKExamples/Core/Common
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Core/Common/PermuteSequenceOfIndices/
  COMPONENT Code
  )


enable_testing()
add_test(NAME PermuteSequenceOfIndicesTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/PermuteSequenceOfIndices)

