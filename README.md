# Foundations of IoT — Laboratory Submissions

**Registration Number:** `25011102002`  
**Repository:** `25011102002_FIoT_LAB`

This repository contains the Foundations of IoT laboratory work arranged in the order of the weekly schedule. The experiments are grouped by the hardware platform used, with separate task directories wherever an evaluation contains multiple parts.

> The submission begins at CAT2. CAT1 is intentionally not included in this repository.

## Repository layout

```text
25011102002_FIoT_LAB/
├── README.md
├── .gitignore
├── 8051/
│   ├── CAT2/TASK2B/
│   ├── CAT3/TASK3A/
│   ├── CAT4/TASK4A/
│   ├── CAT5/TASK5A/
│   ├── CAT6/TASK6A/
│   └── CAT7/
│       ├── TASK7A/
│       ├── TASK7B/
│       └── TASK7C/
└── STM32/
    ├── CAT8/   (TASK8A–TASK8C)
    ├── CAT9/   (TASK9A–TASK9B)
    ├── CAT10/  (TASK10A–TASK10C)
    ├── CAT11/  (TASK11A–TASK11B)
    ├── CAT12/  (TASK12A–TASK12C)
    ├── CAT13/  (TASK13)
    ├── CAT14/  (TASK14)
    └── CAT15/  (TASK15)
```

Every individual task directory contains its README, required source/project files and a `circuit.png` connection diagram. Where the assignment is divided into parts, each part is kept in its own `TASKxA`, `TASKxB`, or `TASKxC` directory.

## Week-wise experiment index

| Week | Repository folder | Platform | Experiment / task |
|---:|---|---|---|
| 2 | `8051/CAT2/TASK2B` | AT89S52 | Development-board toolchain setup and bare-metal LED GPIO blink |
| 3 | `8051/CAT3/TASK3A` | AT89S52 | Timer-based LED patterns and push-button interrupt control |
| 4 | `8051/CAT4/TASK4A` | AT89S52 | Matrix-keypad interface with LED and seven-segment output |
| 5 | `8051/CAT5/TASK5A` | AT89S52 | Hardware timer, LED fading/PWM, waveform generation and optional stepper control |
| 6 | `8051/CAT6/TASK6A` | AT89S52 | UART driver, serial transmission/reception and terminal echo |
| 7 | `8051/CAT7/TASK7A–TASK7C` | AT89S52 | 16×2 LCD initialization, dynamic display and keypad-based character movement |
| 8 | `STM32/CAT8/TASK8A–TASK8C` | STM32F401RE Nucleo | GPIO output, switch input, debouncing and press-duration handling |
| 9 | `STM32/CAT9/TASK9A–TASK9B` | STM32F401RE Nucleo | USART2 terminal communication and string-command LED control |
| 10 | `STM32/CAT10/TASK10A–TASK10C` | STM32F401RE + Wemos D1 mini | UART bridge, ESP8266 AT-command interface and Wi-Fi sensor-data transport |
| 11 | `STM32/CAT11/TASK11A–TASK11B` | STM32F401RE + ESP8266 | HTTP server using ESP8266 AT commands and Node-RED as an HTTP client |
| 12 | `STM32/CAT12/TASK12A–TASK12C` | STM32F401RE Nucleo | On-board LED, switch state retention and short/long-press detection |
| 13 | `STM32/CAT13/TASK13` | STM32F401RE + BME280 | BME280 I²C sensing with Bosch SensorAPI, HTTP/JSON and Node-RED analytics |
| 14 | `STM32/CAT14/TASK14` | STM32F401RE + BME280 + ESP8266 | MQTT publish/subscribe using the custom ESP8266 interface |
| 15 | `STM32/CAT15/TASK15` | STM32F401RE IoT system | Integrated environmental monitoring and MQTT/Node-RED/API workflow |

The folder numbers follow the week-wise sequence supplied for the course. For example, the HTTP-server work is stored under CAT11 (Week 11), even where an individual assignment sheet carries an earlier CAT10C label.

## CAT15 project scope

CAT15 is the Week 15 integrated IoT project. The repository includes the embedded STM32/BME280/ESP8266-MQTT project and its circuit diagram. The Node-RED flow export, dashboard configuration and API-server source are not included in the current upload; the CAT15 README identifies these as separate application-side deliverables. Add the actual files if they are required by the faculty's Week 15 rubric.

## README documentation standard

Each task README records the information requested in the assessment sample:

1. **EXP** — experiment/evaluation identifier.
2. **DATE** — date of the lab activity.
3. **NAME OF EXP** — experiment title as provided in the assignment material.
4. **HARDWARE SETUP / PLATFORM** — board, microcontroller, modules and peripherals.
5. **TASK NO** — task or subdivision identifier.
6. **Circuit Diagram** — embedded using the relative path `circuit.png`.
7. **Core Logic / Pseudocode / Code Base** — a summary of the wiring, operation and relevant source files.
8. **INFERENCE** — the expected or observed result and what the task demonstrates.

## Project files and diagrams

- **8051 projects:** Embedded C source, Keil C51 project files, startup assembly, supporting driver files and retained HEX output where supplied.
- **STM32 projects:** CubeMX `.ioc` configuration, `Core/` application files, `Drivers/` HAL/CMSIS dependencies, Keil MDK-ARM project files and supporting firmware assets.
- **Circuit diagrams:** Each firmware task has its own `circuit.png` in the same directory as its README. The diagram is intended to show the relevant MCU/board, connected pins, peripherals, supply and ground connections.
- **Subdivided experiments:** Each task part is separated into its own task folder so that its README and supporting project files remain together.

## Ignore rules and repository hygiene

The `.gitignore` file is retained exactly as provided in the supplied sample. It excludes IDE-specific user settings, generated listings, object/intermediate files and operating-system metadata while allowing `.hex` firmware files to remain in version control. Avoid adding temporary build directories, editor caches or unrelated files.

## Pre-submission checklist

- [ ] Repository name is `25011102002_FIoT_LAB`.
- [ ] Both platform folders (`8051/` and `STM32/`) are present.
- [ ] CAT2 through CAT15 are present in their respective platform folders; CAT1 is omitted.
- [ ] Every task subdivision contains its README and the necessary project/source files.
- [ ] Every firmware task contains `circuit.png`.
- [ ] Project files open in the intended Keil/CubeMX toolchain.
- [ ] Wi-Fi credentials and other local configuration values are checked before use and are not committed if private.
- [ ] The pushed GitHub repository is accessible to the evaluator.

## Verification note

The repository contents and required file presence have been checked locally. The firmware has not been rebuilt or hardware-tested in this environment; compile and verify the projects with the target boards and the required Keil/CubeMX toolchain before relying on runtime results.
