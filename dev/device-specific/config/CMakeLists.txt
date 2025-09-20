add_library(device-config-intf INTERFACE)
target_include_directories(
  device-config-intf
  INTERFACE
  .
)

add_library(device-config OBJECT)
target_sources(
  device-config
  PRIVATE
  startup_stm32f411xe.s
  stm32f4xx_hal_msp.c
  stm32f4xx_it.c
  syscalls.c
  sysmem.c
)

target_link_libraries(
  device-config 
  PUBLIC 
  device-config-intf
)