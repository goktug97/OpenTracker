cmake_minimum_required( VERSION 2.8 )
project( OpenTrackerExample )

set( CMAKE_BUILD_TYPE "Release" )
set( CMAKE_CXX_FLAGS "-std=c++11 -O3 -DUSE_MULTI_THREAD -pthread" )

find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_DIRS} )

include_directories( "/home/goktug/OpenTracker" )
find_library(/home/goktug/OpenTracker/eco/libecotracker.so /usr/local/lib)

add_executable( run_opentracker_example.bin run_opentracker_example.cc )

target_link_libraries( run_opentracker_example.bin ${OpenCV_LIBS} /home/goktug/OpenTracker/eco/libecotracker.so) # ${OpenTracker_LIBS} )
