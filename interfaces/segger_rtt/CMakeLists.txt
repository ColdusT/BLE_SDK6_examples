cmake_minimum_required(VERSION 3.16)

project(${DEVICE_NAME} LANGUAGES C CXX ASM)
#Full SDK builds
set(BUILD_FOR_531 TRUE)
set(BUILD_FOR_585 TRUE)
set(BUILD_FOR_586 TRUE)

#Peripheral example builds
set(BUILD_FOR_531_PERIPHERAL_EXAMPLE FALSE)
set(BUILD_FOR_585_PERIPHERAL_EXAMPLE FALSE)
set(BUILD_FOR_586_PERIPHERAL_EXAMPLE FALSE)

message("DEVICE_NAME = ${DEVICE_NAME}")
message("DIALOG_SDK_PATH = ${DIALOG_SDK_PATH}")
message("DIALOG_EXAMPLE_PATH = ${DIALOG_EXAMPLE_PATH}")
message("GCC_TOOLCHAIN_PATH = ${GCC_TOOLCHAIN_PATH}")

set(CMAKE_VERBOSE_MAKEFILE OFF)

FILE(GLOB_RECURSE rtt segger_rtt/RTT/*.c)

LIST(APPEND userSourceFiles ${rtt} )
include_directories(segger_rtt/RTT)

include (${DIALOG_EXAMPLE_PATH}/build_utils/gcc/example_build.cmake)

