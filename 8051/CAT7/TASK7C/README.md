# EXPERIMENT DETAILS

**EXP:** CONTINUOUS ASSESSMENT 7

**DATE:** 24/08/2026

**REGISTRATION NUMBER:** `25011102002`

**TASK NO:** `TASK7C`

**NAME OF EXP:** 16x2 LCD Driver Development and Dynamic Display Control

**HARDWARE SETUP / PLATFORM:** AT89S52 Microcontroller + Keil µVision

---

## TASK 7C : 4x4 Keypad-Based Character Movement

### 1. Hardware Setup

A 4x4 keypad provides directional input for moving a character around the two rows of a 16x2 LCD.

- **Microcontroller:** AT89S52
- **LCD:** 16x2 HD44780-compatible, 4-bit mode
- **LCD RS:** P2.0
- **LCD E:** P2.1
- **LCD D4-D7:** P2.4-P2.7
- **LCD RW:** GND
- **Keypad:** 4x4 matrix keypad
- **Keypad Rows:** P1.0-P1.3
- **Keypad Columns:** P1.4-P1.7
- **Power Supply:** 5V DC
- **Crystal Frequency:** 11.0592 MHz

The LCD uses P2.0/P2.1 for RS/E and P2.4-P2.7 for its data bus. Keypad rows and columns occupy P1.0-P1.7. RW is connected to GND on the 5V HD44780-compatible display.

### 2. Circuit Diagram

![Circuit Diagram](circuit.png)

### 3. Core Logic / Pseudocode / Code Base

**Working Principle:**

After placing 'A' on the display, the firmware repeatedly scans the keypad. Keys 2, 8, 4 and 6 provide the up, down, left and right movement commands.

**Key Controls:**

- **2:** Move Up
- **8:** Move Down
- **4:** Move Left
- **6:** Move Right

The character is kept within the 16 columns and 2 rows of the LCD. A debounce check is used so that one key press produces one movement.

**Pseudocode:**

1. Initialize the LCD and display the character 'A'.
2. Scan the 4x4 keypad.
3. Check whether key 2, 8, 4 or 6 is pressed.
4. Apply the corresponding row or column movement.
5. Keep the character within the LCD boundaries.
6. Clear the previous character position.
7. Display the character at its new position.
8. Repeat continuously.

**Firmware Output:**

The compiled HEX file is saved at `Objects/TASK7C.hex`.

**Code Base:**

The program is written in Embedded C using Keil C51.

- `keypad_scan()` detects keypad input.
- `move_character()` updates the character position.
- `lcd_goto()` selects the LCD row and column.
- `lcd_data()` displays the character.
- A 20 ms debounce check avoids repeated movement from one key press.

### 4. Inference

The character position changes in response to the four direction keys and remains within the available LCD rows and columns. The task brings together keypad scanning and LCD cursor positioning on the AT89S52.
