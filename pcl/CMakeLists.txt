cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
project(PCL_TEST)
find_package(PCL 1.3 REQUIRED COMPONENTS common io visualization)
find_package(Boost 1.54.0 COMPONENTS program_options system thread REQUIRED)
include_directories(
${PCL_INCLUDE_DIRS}
${Boost_INCLUDE_DIRS}
)
link_directories(${PCL_LIBRARY_DIRS})

add_definitions(${PCL_DEFINITIONS})
add_executable(pcd_read_test pcd_read.cpp)
target_link_libraries(pcd_read_test ${Boost_LIBRARIES} ${PCL_LIBRARIES})

add_executable (cloud_viewer cloud_viewer.cpp)
target_link_libraries (cloud_viewer ${Boost_LIBRARIES} ${PCL_LIBRARIES})

add_executable (cloud_viewer_bin bin_read.cpp)
target_link_libraries (cloud_viewer_bin ${Boost_LIBRARIES} ${PCL_LIBRARIES})

