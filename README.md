# Automatic Water Level Controller 💧

An Arduino Nano based automatic water level controller prototype using an HC-SR04 ultrasonic sensor, 16×2 LCD and relay-controlled pump.

## Project status

**Working prototype / demonstration project**

The controller measures the distance from the top of a tank to the water surface, converts the measurement into a water-level percentage, displays the status on an LCD, and controls a pump in automatic or manual mode.

## Main features

- Ultrasonic, non-contact water-level measurement
- Real-time water-level percentage on a 16×2 LCD
- Automatic pump control
- Manual pump-control mode
- User tank-depth calibration
- Calibration value stored in Arduino EEPROM
- Relay-controlled pump output
- Hand-etched single-layer prototype PCB

## Hardware

| Component | Purpose |
|---|---|
| Arduino Nano (ATmega328P) | Main controller |
| HC-SR04 | Water-level measurement |
| 16×2 LCD | Status display |
| Relay | Pump switching |
| Push button / switch controls | Calibration and manual control |
| 7805 regulator | 5 V regulation |
| 12 V adapter | Prototype power supply |

## Pin mapping

| Arduino Nano pin | Function |
|---|---|
| D2–D7 | 16×2 LCD interface |
| D8 | HC-SR04 TRIG |
| D9 | HC-SR04 ECHO |
| D10 | Calibration / set control |
| D11 | Auto / Manual mode input |
| D12 | Relay / pump output |

## Working principle

1. The Arduino sends a short trigger pulse to the HC-SR04.
2. The sensor returns an echo whose duration represents the distance to the water surface.
3. The controller converts the distance into inches.
4. The calibrated tank depth is used to calculate the water-level percentage.
5. In automatic mode, the pump starts when the reported level is below 30%.
6. The pump stops when the reported level reaches above 99%.
7. In manual mode, the pump can be toggled directly.
8. The LCD continuously displays level, pump status and operating mode.

## Calibration

The project uses a calibration action to measure the tank depth. The value is stored in EEPROM so the calibration is retained after power is removed.

## Repository structure

```text
Automatic_water_leval_controller/
├── README.md
├── src/
│   └── Automatic_Water_Level_Controller.ino
└── docs/
    └── PROJECT_REPORT.md
```

## Prototype scope

This repository documents the current college/hobby-level prototype. The project report describes possible future upgrades such as ESP32-based IoT monitoring, mobile dashboards, alerts, improved outdoor enclosures, industrial-grade sensors and professionally manufactured PCBs.

## Safety

The prototype includes relay switching intended for the documented load range. Any mains-powered pump installation should use appropriate electrical protection, isolation, enclosure, wiring, earthing and a qualified person where required. Do not work on exposed mains wiring while energized.

## Author

**D_LABS**

Real Electronics. Real Engineering. Real Projects.

Instagram: @d_labs_pro  
Email: dlabspro@gmail.com
