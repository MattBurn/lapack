# add_subdirectory(SRC)
# if(BUILD_TESTING)
#   add_subdirectory(TESTING)
# endif()
# configure_file(${CMAKE_CURRENT_SOURCE_DIR}/blas.pc.in ${CMAKE_CURRENT_BINARY_DIR}/blas.pc @ONLY)
# install(FILES
#   ${CMAKE_CURRENT_BINARY_DIR}/blas.pc
#   DESTINATION ${PKG_CONFIG_DIR}
#   COMPONENT Development
#   )
cmake_minimum_required(VERSION 3.14)
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Debug or Release")
endif()
project(BLAS
LANGUAGES C Fortran
VERSION 3.9.0
HOMEPAGE_URL "http://netlib.org/lapack")

set(blas_srcs)
add_subdirectory(SRC)
add_library(blas-lib ${blas_srcs})

set_target_properties(
  blas-lib
  PROPERTIES
  POSITION_INDEPENDENT_CODE TRUE
  OUTPUT_NAME "${PROJECT_NAME}"
  VERSION "${PROJECT_VERSION}"
  SOVERSION "${PROJECT_VERSION_MAJOR}"
  Fortran_MODULE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/include"
)
target_include_directories(
  blas-lib
  INTERFACE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/include>
  $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)