# FreeRTOS-IMU-Visualiser-STM32F303K8-MPU-6050-MAX7219
•Developed a multi-task FreeRTOS firmware on STM32F303K8 where one task samples MPU-6050 IMU data over I2C at 500 Hz while another renders a real-time tilt indicator on a MAX7219 8×8 LED matrix via SPI.
•Implemented a bare-metal SPI driver for the MAX7219 (manual chip-select control and 16-bit register writes) and used SPI DMA with a binary semaphore to signal transfer completion.
•Designed a FreeRTOS queue for lock-free data exchange between acquisition and display tasks and profiled runtime using SysTick/FreeRTOS stats, reducing CPU overhead of display updates by ~60% compared to blocking SPI.
