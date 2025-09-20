add_library(device-config-intf INTERFACE)

target_include_directories(
  device-config-intf
  INTERFACE
  .
)

target_include_directories(
  ${CMAKE_PROJECT_NAME} 
  PRIVATE
  .
)

target_link_libraries(
  ${CMAKE_PROJECT_NAME} 
  PRIVATE
  device-config
  device-config-intf
  micro-support
  micro-support-intf
)

set_target_properties(${CMAKE_PROJECT_NAME} PROPERTIES ADDITIONAL_CLEAN_FILES ${CMAKE_PROJECT_NAME}.map)