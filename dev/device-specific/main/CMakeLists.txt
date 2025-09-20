target_sources(
  ${CMAKE_PROJECT_NAME} 
  PRIVATE 
  main.c
)

target_include_directories(
  ${CMAKE_PROJECT_NAME} 
  PRIVATE
  .
)
target_link_libraries(
  ${CMAKE_PROJECT_NAME} 
  PRIVATE
  micro-support
  device-config
)

set_target_properties(${CMAKE_PROJECT_NAME} PROPERTIES ADDITIONAL_CLEAN_FILES ${CMAKE_PROJECT_NAME}.map)