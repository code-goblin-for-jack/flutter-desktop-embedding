cmake_minimum_required(VERSION 3.10)
set(PROJECT_NAME "url_launcher_fde")
project(${PROJECT_NAME} LANGUAGES CXX)

set(PLUGIN_NAME "${PROJECT_NAME}_plugin")

add_library(${PLUGIN_NAME} SHARED
  "url_launcher_plugin.cc"
)
apply_standard_settings(${PLUGIN_NAME})
target_include_directories(${PLUGIN_NAME} INTERFACE
  "${CMAKE_CURRENT_SOURCE_DIR}/include")
target_link_libraries(${PLUGIN_NAME} PRIVATE flutter flutter_wrapper_plugin)
