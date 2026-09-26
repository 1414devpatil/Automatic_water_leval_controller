# Automatic Water Level Controller — Project Report

**Brand:** D_LABS  
**Category:** Embedded Systems / Power Electronics  
**Microcontroller:** Arduino Nano (ATmega328P)  
**Display:** 16×2 LCD  
**Power supply:** 12 V adapter  
**PCB:** Hand-etched single-layer prototype

## 1. Project overview

This project is a working prototype demonstrating automatic water-level monitoring using an ultrasonic sensor and Arduino Nano. The system displays real-time water-level percentage on a 16×2 LCD and controls a water pump through a relay in automatic and manual modes.

The documented prototype is intended as a demonstration/hobby-level system. The report identifies further development paths for residential and agricultural applications.

## 2. Components

- Arduino Nano
- HC-SR04 ultrasonic sensor
- 16×2 LCD
- Relay
- Push buttons / switches
- 7805 regulator
- Jumper wires
- 12 V adapter
- Hand-etched single-layer PCB

## 3. Working principle

The HC-SR04 is mounted above the water surface. The Arduino sends a 10 microsecond trigger pulse on D8 and measures the return pulse on D9.

Distance is calculated as:

`distance (inches) = pulseIn duration / 74 / 2`

The water-level percentage is calculated from the calibrated tank depth:

`percentage = (set_val - distance) × 100 / set_val`

The reported percentage is clamped to a minimum of 0%.

### Pump logic

- **AUTO mode:** below 30% → pump ON
- **AUTO mode:** above 99% → pump OFF
- **MANUAL mode:** push-button control toggles the pump

The LCD displays water level, pump status and operating mode. The loop updates approximately every 500 ms.

## 4. Calibration and EEPROM

The controller can measure the tank depth during calibration and store the value in Arduino EEPROM. This allows the calibration value to remain available after power is removed.

## 5. Key features

- Non-contact water-level measurement
- Real-time LCD indication
- Automatic pump ON/OFF control
- Manual override
- EEPROM calibration storage
- Hand-etched single-layer PCB
- Relay-based pump switching

## 6. Future upgrades documented in the original report

- ESP32-based IoT monitoring
- Blynk or custom mobile dashboard
- SMS / WhatsApp alerts
- Dry-run protection
- Waterproof enclosure
- Industrial-grade waterproof ultrasonic sensor
- Multi-tank monitoring
- Solar-powered operation
- Professional PCB manufacturing

## 7. Applications described in the report

- Home water-tank automation
- Agricultural irrigation
- Apartments
- Schools
- Hostels
- Small industries

## 8. Project scope

This repository documents the current prototype and its source code. It should not be treated as a ready-to-install mains pump controller without appropriate electrical protection, isolation, enclosure, wiring and safety verification.

## 9. About D_LABS

D_LABS focuses on practical electronics projects including embedded systems, PCB design, amplifier builds and repair work.

**Instagram:** @d_labs_pro  
**Email:** dlabspro@gmail.com
