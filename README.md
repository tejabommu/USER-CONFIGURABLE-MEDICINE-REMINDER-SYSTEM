# Medicine Reminder System using LPC2148

## 1. Project Overview

This project implements a medicine reminder system using the LPC2148 ARM7 microcontroller. The system monitors real time using the internal Real Time Clock (RTC) and alerts the user when it is time to take medicine. The device displays current time, date, and reminder information on a 16×2 LCD display. Users can configure the system through a keypad-based menu. When the scheduled medicine time matches the RTC time, a buzzer alert is triggered. The user can acknowledge and stop the alert using an interrupt switch.

The system also calculates and displays the remaining time until the next medicine reminder.

## 2. Objectives

* Provide a simple embedded solution for medicine reminders.
* Demonstrate RTC functionality using LPC2148.
* Implement keypad-based menu navigation.
* Use interrupts for system control.
* Display real-time data on LCD.

## 3. Features

* Real-time clock display (hour, minute, second)
* Date display (day, month, year)
* Day of week display
* Menu interface for editing RTC parameters
* Menu interface for editing medicine timings
* Three configurable medicine reminders
* Automatic buzzer alert at scheduled time
* Interrupt-based menu access
* Interrupt-based buzzer stop
* Display of remaining time until next medicine reminder
* Simulation support in Proteus
* Tested on real LPC2148 hardware

## 4. Hardware Components

* LPC2148 ARM7 Microcontroller
* 16×2 LCD Display (LM016L)
* 4×4 Matrix Keypad
* Active Buzzer
* Two Push Buttons (interrupt switches)
* 10kΩ Pull-up resistors
* Potentiometer for LCD contrast
* 3.3V regulated power supply
* Breadboard / Development board
* Connecting wires

## 5. Software Tools

* Keil uVision IDE
* Embedded C programming language
* Proteus 8 Professional for simulation

## 6. System Working Principle

The RTC module inside the LPC2148 continuously maintains time and date. The microcontroller reads the RTC registers and displays the information on the LCD. A keypad allows the user to open a configuration menu where time, date, and medicine schedules can be modified.

Three medicine reminder times are stored in the system. The program continuously compares the RTC time with these stored reminder times. When the time matches any of the medicine schedules, the buzzer is activated. The buzzer continues to ring for up to one minute unless the user stops it using the interrupt switch.

The system also calculates the difference between the current time and the next medicine schedule and displays the remaining time on the LCD.

## 7. Pin Configuration

### LCD Interface

LCD Data Pins → P0.4 – P0.11

RS → P0.20

RW → P0.19

EN → P0.21

### Buzzer

Buzzer → P0.17

### External Interrupts

EINT0 → P0.16 (Menu open)

EINT1 → P0.14 (Stop buzzer)

### Keypad Interface

Rows → P1.16 – P1.19

Columns → P1.20 – P1.23

## 8. System Operation

1. The system initializes LCD, RTC, keypad, interrupts, and buzzer.
2. The LCD continuously displays the current time and date.
3. The program checks medicine schedules.
4. When a reminder time is reached, the buzzer alert activates.
5. The user can stop the buzzer using the interrupt switch.
6. Pressing the menu interrupt opens the configuration menu.
7. The user can edit RTC parameters or medicine schedules using the keypad.

## 9. Proteus Simulation Setup

1. Open Proteus and create a new schematic.
2. Add LPC2148 microcontroller.
3. Add LM016L LCD module.
4. Add keypad component.
5. Add buzzer and switches.
6. Connect all pins according to the pin configuration.
7. Compile the program in Keil and generate the HEX file.
8. Load the HEX file into the LPC2148 component.
9. Run the simulation.

## 10. Hardware Implementation

The system was implemented on an LPC2148 development board. The LCD, keypad, buzzer, and interrupt switches were connected according to the pin configuration. The program was compiled using Keil and flashed into the microcontroller. The hardware successfully displayed real-time clock information and generated medicine alerts.

## 11. Project Folder Structure

```
medicine_reminder/
│
├── mini.c
├── lcd.c
├── rtc.c
├── keypad.c
├── interrupt.c
├── buzzer.c
├── defines.h
└── README.md
```

## 12. Applications

* Personal medicine reminder system
* Elderly healthcare assistance devices
* Embedded systems educational project
* Real-time monitoring systems

## 13. Future Improvements

* Add support for more medicine reminders
* Implement EEPROM storage for schedules
* Add battery backup for RTC
* Improve user interface with graphical display
* Add wireless notification features
