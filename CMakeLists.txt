cmake_minimum_required (VERSION 2.8.11)
project (libffm)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")

set(CMAKE_INSTALL_PREFIX "${CMAKE_CURRENT_BINARY_DIR}")

include_directories(include)

add_library(ffm
    src/ffm.cpp
    src/timer.cpp
)

add_executable(ffm-train src/ffm-train.cpp)
add_executable(ffm-predict src/ffm-predict.cpp)
target_link_libraries(ffm-train ffm)
target_link_libraries(ffm-predict ffm)

