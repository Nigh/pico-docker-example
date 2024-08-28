cmake_minimum_required(VERSION 3.12)

# Pull in SDK (must be before project)
include($ENV{PICO_SDK_PATH}/external/pico_sdk_import.cmake)

project(pico_docker_example C CXX ASM)

pico_sdk_init()

add_subdirectory(blink_simple)
