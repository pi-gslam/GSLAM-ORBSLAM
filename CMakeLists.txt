cmake_minimum_required(VERSION 2.8)
project(gslam_orbslam)

include(cmake/PICMake.cmake)
list(APPEND CMAKE_CXX_FLAGS -std=c++11)
pi_collect_packages(VERBOSE REQUIRED GSLAM OpenCV Eigen3)
pi_add_target(gslam_orbslam SHARED src REQUIRED GSLAM OpenCV Eigen3 DEPENDENCY -lboost_serialization -lboost_system -lboost_thread)
pi_report_targets()
pi_install(TARGETS gslam_orbslam LIB_DESTINATION lib)

