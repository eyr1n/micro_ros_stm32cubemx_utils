cmake_minimum_required(VERSION 3.22)

project(micro_ros_stm32cubemx_utils LANGUAGES C CXX)

add_library(${PROJECT_NAME} INTERFACE)

target_sources(${PROJECT_NAME} INTERFACE
  extra_sources/custom_memory_manager.c
  extra_sources/microros_allocators.c
  extra_sources/microros_time.c
)

target_include_directories(${PROJECT_NAME} INTERFACE
  microros_static_library/libmicroros/microros_include
)

target_link_libraries(${PROJECT_NAME} INTERFACE
  ${CMAKE_CURRENT_SOURCE_DIR}/microros_static_library/libmicroros/libmicroros.a
)
