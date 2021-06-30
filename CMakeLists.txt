cmake_minimum_required (VERSION 3.1)
project (qwt VERSION 6.2.0 LANGUAGES CXX)

option (WITH_PLOT "Whether to build plot" ON)
option (WITH_SVG "Whether to build svg" ON)
option (WITH_OPENGL "Whether to build opengl" ON)
option (WITH_POLAR "Whether to build polar" ON)
option (WITH_WIDGETS "Whether to build widgets" ON)

option (WITH_EXAMPLES "Whether to include examples" OFF)

option (BUILD_SHARED_LIBS "Build shared/static libs" ON)
option (USE_QT6 "qt 6.x" OFF)

include (GNUInstallDirs)

set (QWT_VER_MAJ 6)
set (QWT_VER_MIN 2)
set (QWT_VER_PAT 0)
set (QWT_VERSION ${QWT_VER_MAJ}.${QWT_VER_MIN}.${QWT_VER_PAT})

if (USE_QT6)
  find_package (Qt6 COMPONENTS Concurrent OpenGL OpenGLWidgets PrintSupport Svg Widgets REQUIRED CONFIG)
else ()
  find_package (Qt5 COMPONENTS Concurrent OpenGL PrintSupport Svg Widgets REQUIRED CONFIG)
endif ()

add_subdirectory (src)

if (WITH_EXAMPLES)
  add_subdirectory(examples)
endif()
