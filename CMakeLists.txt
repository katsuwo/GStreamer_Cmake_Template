cmake_minimum_required(VERSION 3.17)
project(GStreamerTemplate)
find_package(PkgConfig REQUIRED)
pkg_check_modules(LIBGST REQUIRED gstreamer-1.0)
set(CMAKE_CXX_STANDARD 14)

include_directories(.)
include_directories(${LIBGST_INCLUDE_DIRS})
add_executable(GStreamerTemplate
        mp3send_multisrc_udpsink.c)
target_link_libraries(GStreamerTemplate
        ${LIBGST_LIBRARIES})