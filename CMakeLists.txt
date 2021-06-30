cmake_minimum_required (VERSION 3.18)
project (qwt VERSION 6.3.0 LANGUAGES CXX)

option (WITH_PLOT "Whether to build plot" ON)
option (WITH_SVG "Whether to build svg" ON)
option (WITH_OPENGL "Whether to build opengl" ON)
option (WITH_POLAR "Whether to build polar" ON)
option (WITH_WIDGETS "Whether to build widgets" ON)

option (WITH_EXAMPLES "Whether to include examples" OFF)

option (BUILD_SHARED_LIBS "Build shared/static libs" ON)
set (QWT_QT_MAJOR_VERSION 6 CACHE STRING "Qt version")

include (GNUInstallDirs)

set (QWT_VER_MAJ 6)
set (QWT_VER_MIN 3)
set (QWT_VER_PAT 0)
set (QWT_VERSION ${QWT_VER_MAJ}.${QWT_VER_MIN}.${QWT_VER_PAT})

set(QWT_QT_COMPONENTS Concurrent OpenGL PrintSupport Svg Widgets)
if (QWT_QT_MAJOR_VERSION VERSION_GREATER 5)
  list (APPEND QWT_QT_COMPONENTS OpenGLWidgets)
endif ()

find_package(Qt${QWT_QT_MAJOR_VERSION} COMPONENTS ${QWT_QT_COMPONENTS} REQUIRED CONFIG)

add_subdirectory (src)

if (WITH_EXAMPLES)
  add_subdirectory(examples)
endif()
