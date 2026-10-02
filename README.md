# 🔧 Embedded Systems Roadmap

A structured path from beginner to job-ready embedded engineer. Each phase is split into **Theory** (what to learn) and **Practical** (what to build).

> Track progress by ticking the checkboxes. Fork this repo and make it yours.

---

## 📑 Table of Contents

1. [Phase 1: Foundations](#phase-1-foundations)
2. [Phase 2: Microcontroller Basics](#phase-2-microcontroller-basics)
3. [Phase 3: Communication Protocols](#phase-3-communication-protocols)
4. [Phase 4: RTOS and Architecture](#phase-4-rtos-and-architecture)
5. [Phase 5: Connectivity and IoT](#phase-5-connectivity-and-iot)
6. [Phase 6: Tools and Best Practices](#phase-6-tools-and-best-practices)
7. [Phase 7: Specialization](#phase-7-specialization)
8. [Capstone Projects](#capstone-projects)
9. [Resources](#resources)

---

## Phase 1: Foundations
**Duration:** 4-6 weeks

### 📘 Theory
- [ ] C programming: pointers, structs, unions, enums
- [ ] Bitwise operations, masking, shifting
- [ ] `volatile`, `const`, `static` keywords and when to use them
- [ ] Memory layout: stack, heap, `.data`, `.bss`, `.text`
- [ ] Number systems: binary, hex, two's complement
- [ ] Digital logic: gates, flip-flops, counters, multiplexers
- [ ] Analog basics: Ohm's law, voltage dividers, op-amps, filters
- [ ] ADC/DAC concepts: resolution, sampling rate, Nyquist
- [ ] Reading datasheets and schematics

### 🛠️ Practical
- [ ] Write C programs for bit manipulation (set, clear, toggle, check)
- [ ] Implement a circular buffer and linked list in C
- [ ] Build circuits on a breadboard: LED, button, voltage divider
- [ ] Use a multimeter to measure voltage, current, continuity
- [ ] Read a datasheet and extract pinout, ratings, timing

---

## Phase 2: Microcontroller Basics
**Duration:** 6-8 weeks

### 📘 Theory
- [ ] Microcontroller architecture: CPU, memory, peripherals, buses
- [ ] ARM Cortex-M overview: registers, NVIC, SysTick
- [ ] GPIO modes: input, output, push-pull, open-drain, pull-up/down
- [ ] Interrupts: ISR rules, latency, debouncing
- [ ] Timers: counters, input capture, output compare
- [ ] PWM: duty cycle, frequency, applications
- [ ] ADC: conversion modes, reference voltage
- [ ] Clock tree and power management

### 🛠️ Practical
- [ ] Blink LED on Arduino/ESP32, then on STM32
- [ ] Button input with interrupt and software debounce
- [ ] PWM motor speed and LED dimming
- [ ] Read analog sensor (LDR, potentiometer, LM35) via ADC
- [ ] **Bare-metal:** blink LED by writing directly to registers (no HAL)
- [ ] Build a hardware timer-based delay without `delay()`

---

## Phase 3: Communication Protocols
**Duration:** 4-6 weeks

### 📘 Theory
- [ ] UART: baud rate, framing, parity, flow control
- [ ] SPI: modes (CPOL/CPHA), chip select, full duplex
- [ ] I2C: addressing, ACK/NACK, clock stretching, pull-ups
- [ ] CAN bus: arbitration, frames, bit timing
- [ ] RS-232 vs RS-485 vs TTL levels
- [ ] Protocol comparison: speed, wiring, use cases

### 🛠️ Practical
- [ ] UART: print debug logs and parse commands from a serial terminal
- [ ] I2C: read a sensor (MPU6050, BMP280) and show on OLED
- [ ] SPI: interface SD card or flash memory (W25Qxx)
- [ ] CAN: two-node message exchange
- [ ] Capture and decode all four protocols with a logic analyzer
- [ ] Inspect signals with an oscilloscope

---

## Phase 4: RTOS and Architecture
**Duration:** 6-8 weeks

### 📘 Theory
- [ ] Super-loop vs interrupt-driven vs RTOS designs
- [ ] Tasks, scheduling, priorities, preemption
- [ ] Queues, semaphores, mutexes, event groups
- [ ] Priority inversion and deadlock
- [ ] Finite state machines
- [ ] DMA: how it works and why it matters
- [ ] Low-power modes: sleep, stop, standby
- [ ] Bootloader basics, linker scripts, startup code

### 🛠️ Practical
- [ ] FreeRTOS: run multiple tasks (LED, sensor, UART)
- [ ] Pass data between tasks using queues
- [ ] Protect a shared resource with a mutex
- [ ] Reproduce and fix a priority inversion bug
- [ ] Implement a state machine (traffic light, vending machine)
- [ ] UART or ADC transfer using DMA
- [ ] Measure and reduce current in sleep mode
- [ ] Write a simple custom bootloader

---

## Phase 5: Connectivity and IoT
**Duration:** 4-6 weeks

### 📘 Theory
- [ ] Wi-Fi, BLE, LoRa/LoRaWAN, Zigbee: range, power, use cases
- [ ] TCP/IP basics on constrained devices
- [ ] MQTT: broker, topics, QoS, retained messages
- [ ] HTTP/REST vs MQTT for IoT
- [ ] JSON and CBOR data formats
- [ ] OTA update architecture

### 🛠️ Practical
- [ ] ESP32 publishes sensor data to an MQTT broker
- [ ] Build a dashboard (Node-RED, Grafana, or ThingsBoard)
- [ ] BLE peripheral with custom GATT service
- [ ] LoRa point-to-point link between two nodes
- [ ] Implement OTA firmware update on ESP32

---

## Phase 6: Tools and Best Practices
**Ongoing**

### 📘 Theory
- [ ] Git workflow: branches, pull requests, tags
- [ ] Debug interfaces: JTAG, SWD
- [ ] Build systems: Make, CMake
- [ ] Coding standards: MISRA C basics
- [ ] Testing: unit tests, hardware-in-the-loop
- [ ] PCB design fundamentals: schematic, layout, decoupling, grounding

### 🛠️ Practical
- [ ] Debug with GDB + OpenOCD (breakpoints, watch variables, inspect registers)
- [ ] Set up a CMake-based STM32 project
- [ ] Write unit tests with Unity/Ceedling
- [ ] Run static analysis (cppcheck, clang-tidy)
- [ ] Design a simple PCB in KiCad and get it fabricated

---

## Phase 7: Specialization
Pick one or more tracks.

### 🔐 Track A: IoT and Embedded Security

**📘 Theory**
- [ ] Threat modeling for embedded devices
- [ ] Secure boot and chain of trust
- [ ] Cryptography basics: AES, RSA, ECC, hashing, TLS
- [ ] Firmware extraction and reverse engineering concepts
- [ ] Hardware attack surface: UART, JTAG/SWD, SPI flash
- [ ] Side-channel and fault injection basics
- [ ] Common IoT vulnerabilities (OWASP IoT Top 10)

**🛠️ Practical**
- [ ] Find UART/JTAG pins on a router or IoT device
- [ ] Dump firmware from SPI flash (flashrom + CH341A)
- [ ] Analyze firmware with Binwalk and Ghidra
- [ ] Emulate firmware with QEMU/Firmadyne
- [ ] Implement TLS/MQTTS on ESP32
- [ ] Enable secure boot and flash encryption on ESP32
- [ ] Practice with CTFs and vulnerable firmware (e.g., DVRF, OWASP IoTGoat)

### 🏭 Track B: Industrial and Controls

**📘 Theory**
- [ ] PLC architecture and scan cycle
- [ ] Ladder logic, function block diagram, structured text
- [ ] Modbus RTU/TCP, PROFIBUS, OPC UA
- [ ] PID control theory
- [ ] Sensors and actuators in automation

**🛠️ Practical**
- [ ] Ladder programs in a PLC simulator (motor start/stop, timers, counters)
- [ ] Modbus master/slave between two devices
- [ ] Implement PID for temperature or motor speed control

### 🐧 Track C: Embedded Linux and TinyML

**📘 Theory**
- [ ] Linux boot process, device tree, kernel modules
- [ ] Yocto/Buildroot basics
- [ ] Neural network basics and quantization

**🛠️ Practical**
- [ ] Boot Raspberry Pi/BeagleBone with a custom Buildroot image
- [ ] Write a simple Linux character device driver
- [ ] Deploy a TensorFlow Lite Micro model (keyword spotting, gesture recognition)

---

## Capstone Projects

| # | Project | Skills Covered |
|---|---------|----------------|
| 1 | Sensor data logger | I2C, SPI, SD card, timers |
| 2 | RTOS multi-sensor system | FreeRTOS, queues, UART |
| 3 | IoT node with OTA | Wi-Fi/BLE, MQTT, OTA |
| 4 | Custom PCB + bare-metal firmware | KiCad, registers, debugging |
| 5 | Firmware security analysis | Extraction, Ghidra, reporting |

---

## Resources

### 📚 Books
- *Making Embedded Systems*: Elecia White
- *Mastering STM32*: Carmine Noviello
- *The Definitive Guide to ARM Cortex-M3/M4*: Joseph Yiu
- *The Art of Electronics*: Horowitz & Hill
- *Practical IoT Hacking*: Fotios Chantzis et al.

### 🌐 Websites
- [Embedded Artistry](https://embeddedartistry.com)
- [FreeRTOS Docs](https://www.freertos.org)
- [Interrupt by Memfault](https://interrupt.memfault.com)
- [Hackaday](https://hackaday.com)
- [OWASP IoT Project](https://owasp.org/www-project-internet-of-things/)

### 🧰 Hardware Starter Kit
- STM32 Nucleo / Blue Pill, ESP32 DevKit
- Breadboard, jumper wires, assorted components
- Logic analyzer (Saleae clone), multimeter
- USB-UART adapter, ST-Link/J-Link
- CH341A programmer + SOIC-8 clip (for security track)

---

## 🤝 Contributing

Pull requests are welcome. Add resources, fix errors, or suggest new topics.

## 📄 License

MIT
