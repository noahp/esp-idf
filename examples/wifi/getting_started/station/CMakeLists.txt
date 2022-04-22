# The following five lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

get_filename_component(MEMFAULT_FIRMWARE_SDK memfault-firmware-sdk ABSOLUTE)
include(${MEMFAULT_FIRMWARE_SDK}/ports/esp_idf/memfault.cmake)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
project(wifi_station)

add_custom_command(TARGET ${CMAKE_PROJECT_NAME}.elf
  POST_BUILD
  COMMAND
  python ${MEMFAULT_FIRMWARE_SDK}/scripts/fw_build_id.py ${CMAKE_PROJECT_NAME}.elf)
