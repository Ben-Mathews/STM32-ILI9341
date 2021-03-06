# STM32-ILI9341
Simple driver for ILI9341 320x240 TFT LCD with Touchscreen for STM32 microcontrollers

*Improved, optimized, made hardware-independent against initial [@martnak](https://github.com/martnak/STM32-ILI9341) version*

Requires no DMA or Interrupts while still maintaining very fast screen draws. See performance analysis below

The intent of this library is to provide a really simple way to get ILI9341 projects started without complex methods.
Basic SPI and GPIO inputs/Outputs are enough to use the library.

Contains:
  - main driver for initialization and basic functions "ILI9341_STM32_Driver"
  - GFX driver for advanced functionality (fonts, pictures)
  - <s>Touchscreen driver</s>
  - Example project with CubeMX built for <s>STM32F746ZG</s>STM32L476RG Nucleo board made for [CLion](https://jetbrains.com/clion) IDE
  - Example usage of functions

ILI9341 Driver library for STM32


While there are other libraries for ILI9341 they mostly require either interrupts, DMA or both for fast drawing
The intent of this library is to offer a simple yet still reasonably fast alternatives for those that
do not wish to use interrupts or DMA in their projects.

Library is written for STM32 HAL library and supports STM32CUBEMX. To use the library with Cube software
you need to tick the box that generates peripheral initialization code in their own respective .c and .h file


Performance

Settings:	
  - SPI @ 40MHz 
  - STM32L476RG Nucleo board
  - Redraw entire screen

  Theoretical maximum FPS with 50Mhz SPI calculated to be 32.55 FPS
  
  320x240 = 76800 pixels, each pixel contains 16bit colour information (2x8)
  Theoretical Max FPS: 1/((320x240x16)/40000000)
  
  Actual FPS is ~16.7 (image output)


