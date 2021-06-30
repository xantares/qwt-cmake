

macro (qwt_add_example name)
  add_executable(qwt_example_${name} ${ARGN})
  target_link_libraries (qwt_example_${name} PRIVATE qwt)
  target_include_directories (qwt_example_${name} PRIVATE ${PROJECT_SOURCE_DIR}/classincludes)
  set_target_properties(qwt_example_${name} PROPERTIES AUTOMOC ON UNITY_BUILD OFF)
  target_link_libraries (qwt_example_${name} PRIVATE Qt${QWT_QT_MAJOR_VERSION}::PrintSupport)
endmacro ()

add_subdirectory(animation)
add_subdirectory(barchart)
add_subdirectory(bode)
add_subdirectory(controls)
add_subdirectory(cpuplot)
add_subdirectory(curvedemo)
add_subdirectory(dials)
add_subdirectory(oscilloscope)
add_subdirectory(simpleplot)
add_subdirectory(sinusplot)
add_subdirectory(spectrogram)

