cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(Distance_sensor_display C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pdf_sdk_init()

add_executable(Distance_sensor_display
    src/main.c
    src/hcsr04.c
    src/ssd1306.c)

target_include_directories(Distance_sensor_display PRIVATE include)

target_link_libraries(Distance_sensor_display pico_stdlib hardware_gpio hardware_i2c hardware_timer)

pico_enable_stdio_usb(Distance_sensor_display 1)
pico_enable_stdio_uart(Distance_sensor_display 0)

pico_add_extra_outputs(Distance_sensor_display)
