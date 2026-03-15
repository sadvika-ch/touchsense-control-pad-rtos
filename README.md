# TouchSense Control Pad (RTOS)

## Project Overview

TouchSense Control Pad is a Real-Time Embedded System project developed using **STM32 Microcontroller and FreeRTOS**.

The system uses **touch inputs / push buttons** to control multiple LED tasks. Each button press triggers an event which activates a corresponding RTOS task that controls LED blinking with different timing.

This project demonstrates practical usage of **multitasking, event groups, software timers, mutex synchronization, and UART communication** in FreeRTOS.


## Features

- RTOS based multitasking
- Event-driven task switching
- Multiple LED control tasks
- Emergency mode handling
- Software timers
- Interrupt-based input handling
- UART command interface
- Task health monitoring using `vTaskList()`


## Hardware Components

- STM32 Microcontroller
- Touch / Push Buttons (4 Inputs)
- LEDs (4 Outputs)
- UART Serial Interface
- Development Board


## Software Tools

- STM32CubeIDE
- FreeRTOS
- Embedded C
- STM32 HAL Drivers


## System Tasks

### Control Task
Handles event group bits and activates corresponding LED tasks.

### Emergency Task
Highest priority task. Toggles LED rapidly during emergency mode.

### Task1
Toggles LED every **500 ms**.

### Task2
Toggles LED every **1000 ms**.

### Task3
Toggles LED every **1500 ms**.

### UART Task
Processes user commands and prints system status.


## RTOS Concepts Used

- Tasks
- Mutex (for LED and UART protection)
- Event Groups
- Software Timers
- Interrupt Service Routines (ISR)
- Task Notifications
- Thread Local Storage


## UART Commands

Get system status:
STATUS?

Change system mode:
SET_MODE=EMERG
SET_MODE=TASK1
SET_MODE=TASK2
SET_MODE=TASK3


## Working Principle

1. Button press triggers EXTI interrupt.
2. Interrupt starts a software timer to handle debounce.
3. Timer sets event group bit.
4. Control task reads event bits.
5. Corresponding LED task is resumed.
6. LED toggles based on task timing.


## Learning Outcomes

- Real-Time Operating System concepts
- Task scheduling and synchronization
- Event-driven embedded design
- Interrupt handling in embedded systems
- UART based command processing

