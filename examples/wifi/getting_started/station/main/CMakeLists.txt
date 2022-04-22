idf_component_register(
  SRCS
  "station_example_main.c"
  "memfault_platform_port.c"
  INCLUDE_DIRS
  "."
  ${MEMFAULT_FIRMWARE_SDK}/ports/include
)
