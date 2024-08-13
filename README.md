# Microcontroller Door Lock System

## Overview

This project implements a simple door lock system using an 8051 microcontroller. The system features a keypad for entering a password and an LCD display for user interaction. The system checks the entered password and provides feedback by unlocking the door for a correct password or indicating an incorrect attempt.

## Features

- **LCD Display**: Shows prompts and messages to the user.
- **Keypad Input**: Allows users to enter a password.
- **Password Verification**: Compares entered password with a predefined correct password.
- **Door Lock Control**: Indicates whether the password is correct by controlling an output signal.
- **Timer Functionality**: Provides a delay mechanism for handling incorrect password attempts.

## Components

![BITMAP](https://github.com/user-attachments/assets/ba61740e-7f7c-412c-a060-302536ea1ebe)

- **8051 Microcontroller**: The central controller for the project.
- **LCD Display**: For displaying messages and prompts.
- **Keypad**: For user input.
- **Various I/O Pins**: For controlling and reading from the hardware components.

## Connections

1. **LCD Connections**:
   - Data Pins: Connected to Port 2 (P2).
   - RS and EN Pins: Connected to P3.0 and P3.1 respectively.

2. **Keypad Connections**:
   - Connected to Port 1 (P1).

3. **Output Control**:
   - IN1, IN2, IN3: Connected to control signals that controls the H-bridge, which is responsible for opening the door lock.

## Code Explanation

### Initialization

- **`LCD_INIT`**: Initializes the LCD display by sending necessary commands.

### Main Loop

- **`MAIN`**: Continuously runs the password checking routine.

### Password Checking

- **`CHECK`**: Reads input from the keypad, verifies it against the predefined password, and provides appropriate feedback.

### Keypad Scanning

- **`KEY_SCAN`**: Scans the keypad and returns the ASCII value of the pressed key.

### Display Functions

- **`LCD_COMMAND`**: Sends command instructions to the LCD.
- **`LCD_DATA`**: Sends data (characters) to the LCD.
- **`CLEAR_SCREEN`**: Clears the LCD screen.
- **`NEW_LINE`**: Moves the cursor to the start of the next line on the LCD.

### Feedback Mechanisms

- **`PASS_CORRECT`**: Handles the correct password scenario by setting an output signal and displaying a success message.
- **`PASS_INCORRECT`**: Handles incorrect password scenarios by activating a timer and displaying an error message.

### Timer Function

- **`TIMER`**: Configures and starts a timer to introduce a delay.

## How to Use

1. **Compile** the assembly code and upload it to the 8051 microcontroller.
2. **Connect** the components as described in the "Connections" section.
3. **Power** the system and observe the LCD display.
4. **Enter** the password using the keypad:
   - Enter `1, 2, 3, 4, 5` to unlock.
   - Any other sequence will display an error message.

## Troubleshooting

- **LCD Not Displaying**: Check connections and initialization code. Ensure that the LCD is correctly powered and connected.
- **Keypad Not Responding**: Verify the keypad connections and the scanning routine in the `KEY_SCAN` function.
- **Incorrect Password Handling**: Confirm that the password matches the predefined sequence in the code.


---

Feel free to adjust or add any additional details specific to your project setup or requirements!

