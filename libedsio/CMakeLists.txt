add_library(libedsio STATIC 
  edsio.c
  default.c
  fh.c
  generic.c
  library.c
  maketime.c
  md5c.c
  partime.c
  sha.c
  simple.c
  edsio_edsio.c
  base64.c)

target_include_directories(libedsio PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR} 
  ${ZLIB_INCLUDE_DIRS} 
  ${GLIB_INCLUDE_DIRS})
target_link_libraries(libedsio PUBLIC 
  ${ZLIB_LIBRARIES} 
  ${GLIB_LIBRARIES})
