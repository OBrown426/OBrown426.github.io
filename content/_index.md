+++
title = "Owen Brown"
+++

# About Me

<img src="/profile_pic.jpeg" alt="Profile Picture" width="350" style="display: block; margin: 0 auto;" />

<p style="text-align: center;">
Welcome to my portfolio! I am a passionate lifelong learner and software engineer. My technical interests include Embedded and Real-Time Systems, Unix Operating Systems (I'm particularly fond of NixOS), and incessantly organizing my life with Emacs (I'm an org-mode aficionado). Outside of software, I love to read and practice martial arts.
</p>

## Education

### Master of Software Development (MSD)
**University of Utah, Salt Lake City, UT**
2024 – 2025
GPA: 3.967

### BA Chinese, Minor Computer Science
**University of Utah, Salt Lake City, UT**
2016 – 2022

---

# Projects

## [Automated Hydroponic Control System](https://github.com/OBrown426/embedded-hydroponics-monitor)
*Embedded Systems Capstone | ESP32 | Rust | no_std | Fall 2025*

<div style="display: flex; justify-content: center; gap: 10px; margin: 20px 0; flex-wrap: wrap;">
  <img src="/diy_dwc.jpg" alt="DIY Deep Water Culture System" style="width: 250px; height: auto;" />
  <img src="/hardware.jpg" alt="ESP32 Hardware Setup" style="width: 250px; height: auto;" />
  <img src="/plants.jpg" alt="Growing Plants" style="width: 250px; height: auto;" />
</div>

- Architected real-time embedded firmware with 9 concurrent tasks on resource-constrained hardware (520KB SRAM), implementing cooperative multitasking via Embassy async runtime with bounded channel-based IPC and deterministic timing (100Hz sensor polling, 5-second watchdog intervals).
- Designed six-layer defense-in-depth safety system with dual watchdog architecture (software + hardware WDT), interlock validation, runtime monitoring, and emergency stop mechanisms suitable for safety-critical applications.
- Integrated I2C/1-Wire sensors (pH, TDS, DS18B20 temperature) with real-time temperature compensation, GPIO-controlled actuators, and closed-loop bang-bang control with configurable deadbands and 1-hour stabilization cooldowns.

## MSDscript Language Interpreter & GUI
*CS 6015: Software Engineering, University of Utah – Spring 2025*

- Designed and implemented a functional programming language interpreter in C++23 with recursive descent parser generating Abstract Syntax Trees (AST), supporting first-class functions, closures, lexical scoping, and arithmetic/boolean operations.
- Developed Qt6 desktop GUI with signal/slot architecture for interactive expression parsing and evaluation, with extensive Catch2 test suite including unit tests and randomized input testing.

## WebSocket Chat Server with Client
*CS 6011: Computer Programming, University of Utah – Fall 2024*

- Implemented RFC 6455 WebSocket protocol from scratch in Java with manual frame encoding/decoding, bit manipulation for opcodes/masking, XOR payload unmasking, and SHA-1 cryptographic handshake.
- Architected multithreaded TCP server with thread-per-connection model, synchronized room management, dual HTTP/WebSocket handling, and React frontend with custom JSON-based message protocol.

---

# Experience

## Graduate Teaching Assistant
*Kahlert School of Computing, University of Utah – August 2025 – December 2025*

- Lead daily programming labs and troubleshooting sessions for graduate-level students, mentoring on problem-solving techniques and software development best practices.
- Design assessment rubrics plus code review feedback with attention to detail, improving student code quality.
- Collaborate with faculty to develop course materials on software development lifecycle best practices and contribute to curriculum improvements for 3+ courses.

## Associate Software Engineer
*Navitaire, an Amadeus Company – October 2022 – November 2023*

- Optimized ancillary revenue management systems for 60+ airlines using Microsoft Azure cloud infrastructure.
- Developed Windows Forms GUI applications in C# and created automated installers with WiX toolkit.
- Deployed and configured end-to-end software solutions to client-hosted environments via Remote Desktop Protocol.
- Performed troubleshooting and resolved critical ServiceNow cases by developing SQL database scripts and building API integration tools ensuring compliance with client requirements.
- Executed Root Cause Analysis (RCA) for database system failures with meticulous attention to detail, leveraging telemetry data from Grafana, Dynatrace, Splunk, and SQL Server.
- Facilitated cross-functional project planning and product lifecycle management between engineering and support teams, delivering regular stakeholder updates.

---

# Skills

## Programming
C, C++, Rust, C#, Java, Python, Assembly (ARM), SQL, Bash

## Embedded Systems
Microcontrollers (ESP32, STM32), RTOS Concepts, Bare-Metal Development, Interrupt Handling, Watchdog Timers, Memory-Constrained Programming, Cross-Compilation

## Hardware Interfaces
I2C, SPI, UART, 1-Wire, GPIO, ADC, PWM

## Tools & Debugging
GDB, Logic Analyzer, PlatformIO, OpenOCD, Git, CMake, Cargo, Docker

## Software Engineering
Real-Time Systems, Safety-Critical Design, Sensor Fusion, Closed-Loop Control, Unit Testing (Unity, Catch2), SDLC, Code Review

## Additional
Linux/Unix, .NET, Azure, React, REST APIs, Agile, Technical Documentation

---

# Contact

- **LinkedIn:** [linkedin.com/in/owen-brown-334b6b23b](https://www.linkedin.com/in/owen-brown-334b6b23b/)
- **GitHub:** [github.com/OBrown426](https://github.com/OBrown426)
