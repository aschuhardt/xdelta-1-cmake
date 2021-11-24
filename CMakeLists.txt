cmake_minimum_required(VERSION 3.10 FATAL_ERROR)

project(xdelta VERSION 1.1.0 LANGUAGES C)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GLIB REQUIRED glib)
pkg_check_modules(ZLIB REQUIRED zlib)

add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/libedsio")

add_executable(xdelta
  xdmain.c
  xdelta.c
  getopt.c
  getopt1.c
  xd_edsio.c
  xdapply.c)
target_include_directories(xdelta PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(xdelta PRIVATE libedsio)
