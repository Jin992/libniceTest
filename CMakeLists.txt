cmake_minimum_required(VERSION 3.14)
project(libniceTest C)

set(CMAKE_C_STANDARD 99)

find_package(PkgConfig REQUIRED)
pkg_search_module(GLIB REQUIRED glib-2.0)
message(STATUS ${GLIB_LDFLAGS})

add_executable(libniceTest main.c)
target_include_directories(libniceTest  PRIVATE ${GLIB_INCLUDE_DIRS})
target_link_libraries(libniceTest ${GLIB_LDFLAGS} -lgio-2.0 -lgobject-2.0 -lnice)