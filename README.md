# SCIP-system
SCIP system
# SCIP-system

SCIP-system is an integrated smart physiological monitoring platform consisting of hardware, embedded firmware, and an Android application. The system is designed for wearable or portable physiological signal acquisition, real-time wireless communication, data visualization, and health-related signal analysis.

---

## Project Structure

This repository contains the following parts:

```text
SCIP-system/
├── LICENSE
├── README.md
├── SCIP APP.zip
├── SCIP Firmware.zip
└── SCIP Hardware.zip
```

| File | Description |
|---|---|
| `SCIP Hardware.zip` | Hardware design files of the SCIP device, including circuit design related to power management, core controller, ECG acquisition, SCG sensing, WCT module, and external expansion interfaces. |
| `SCIP Firmware.zip` | Embedded firmware for the SCIP hardware platform. It is responsible for sensor initialization, physiological data acquisition, signal packaging, wireless communication, and interaction with the mobile application. |
| `SCIP APP.zip` | Android application project for real-time physiological monitoring, data visualization, user information management, Bluetooth/NFC communication, and physiological parameter calculation. |
| `LICENSE` | MIT License file. |
| `README.md` | Project introduction and usage documentation. |

---

## System Overview

SCIP-system is composed of three main layers:

1. **SCIP Hardware**  
   The hardware platform integrates multiple physiological sensing modules and a wireless communication core. It supports ECG acquisition, SCG measurement, power management, battery operation, and external signal expansion.

2. **SCIP Firmware**  
   The firmware runs on the embedded controller and controls the acquisition, preprocessing, and transmission of physiological signals. It provides the communication bridge between the hardware sensors and the Android application.

3. **SCIP APP**  
   The Android application receives physiological data through Bluetooth and/or NFC, performs data visualization and processing, and provides user-facing monitoring functions such as ECG display, respiratory signal analysis, heart rate calculation, and data recording.

---

## Hardware Design

The SCIP hardware design is divided into several functional modules:

### 1. Power Module

The power module provides stable supply voltages for the whole system. It includes battery input, voltage regulation, and low-noise power supply design for analog and digital circuits.

Main functions include:

- Battery-powered operation
- 3.3 V system power supply
- 1.8 V low-voltage supply for specific analog or sensor modules
- Power filtering and decoupling
- Separation of analog and digital power domains where necessary

### 2. Core Module

The core module is based on an embedded wireless microcontroller platform. It is responsible for:

- Sensor control
- Data acquisition
- Data processing
- Bluetooth communication
- NFC-related interaction if supported
- Communication with the Android application

The core module also provides GPIO, SPI, I2C, ADC, and other interfaces for connecting different sensing and expansion modules.

### 3. ECG Module

The ECG module is designed for cardiac electrical signal acquisition. It includes the analog front-end, electrode input interface, reference/ground configuration, filtering, and digital communication interface.

Main functions include:

- ECG signal acquisition
- Electrode input connection
- Analog front-end signal conditioning
- Digital output through SPI or other communication interfaces
- Heart rate and waveform monitoring support

### 4. WCT Module

The WCT module is used as part of the ECG reference and signal stabilization design. It helps improve ECG acquisition quality by providing a reference-related circuit structure for physiological signal measurement.

### 5. SCG Module

The SCG module is used for mechanical cardiac activity sensing. It usually relies on motion or vibration sensing components to acquire seismocardiography-related signals.

Main functions include:

- SCG signal acquisition
- Motion or vibration sensing
- I2C/SPI communication with the core controller
- Support for mechanical cardiac activity analysis

### 6. Expansion Interfaces

The hardware includes external expansion interfaces for debugging, testing, and future functional extension.

Possible uses include:

- External sensor connection
- Firmware programming
- Serial debugging
- GPIO testing
- Additional physiological signal acquisition

---

## Firmware Description

The SCIP firmware controls the complete embedded workflow of the device.

Main functions include:

- Hardware initialization
- Sensor configuration
- ECG, SCG, respiratory, PPG, or other physiological data acquisition
- Data buffering and packaging
- Bluetooth communication with the Android application
- NFC-related communication if enabled
- System status monitoring
- Low-power or battery-related control

The firmware should be uploaded to the SCIP hardware after compiling with the corresponding embedded development environment.

> **Note:** Please check the files inside `SCIP Firmware.zip` for the exact development framework, such as ESP-IDF, Arduino, PlatformIO, Keil, or other supported toolchains.

---

## Android Application

`SCIP APP` is an Android application developed for real-time physiological monitoring in combination with the SCIP hardware device.

### Main Features

- Communication with external SCIP device through Bluetooth and NFC
- Real-time physiological data acquisition
- ECG waveform display
- Respiratory signal monitoring
- PPG and blood oxygen-related data processing
- Heart rate and respiratory rate calculation
- Data visualization
- User information management
- CSV data recording and export
- Algorithm-based signal processing, such as moving average smoothing, calibration, and respiratory rate estimation

### Main Components

The Android application contains several functional modules:

| Component | Description |
|---|---|
| Dataset modules | Store and manage physiological data such as ECG, respiratory, and PPG signals. |
| Algorithm modules | Implement signal processing algorithms, including heart rate calibration, moving average smoothing, and respiratory rate calculation. |
| Peripheral modules | Manage Bluetooth, NFC, CSV recording, and external device interaction. |
| UI modules | Provide user interfaces such as main page, information page, homepage, gallery page, and slideshow page. |

---

## System Workflow

The general workflow of SCIP-system is shown below:

```text
Physiological Signals
        ↓
SCIP Hardware Sensors
        ↓
Embedded Firmware
        ↓
Bluetooth / NFC Communication
        ↓
SCIP Android APP
        ↓
Signal Display, Data Storage, and Physiological Parameter Analysis
```

Typical monitored signals include:

- ECG
- Respiratory signal
- PPG signal
- Blood oxygen-related signal
- SCG signal
- Heart rate
- Respiratory rate

---

## Getting Started

### 1. Download the Repository

Clone this repository or download the ZIP package:

```bash
git clone https://github.com/<your-username>/SCIP-system.git
```

Then enter the project folder:

```bash
cd SCIP-system
```

---

### 2. Hardware Design

Unzip the hardware package:

```bash
unzip "SCIP Hardware.zip"
```

Open the hardware design files using the corresponding EDA software.

Depending on the file format, possible tools include:

- Altium Designer
- KiCad
- EasyEDA
- Or other PCB design software

Please check the schematic, PCB layout, BOM, and fabrication files before manufacturing the device.

---

### 3. Firmware Development

Unzip the firmware package:

```bash
unzip "SCIP Firmware.zip"
```

Open the firmware project using the corresponding development environment.

Possible development environments include:

- ESP-IDF
- Arduino IDE
- PlatformIO
- Keil
- STM32CubeIDE
- Other embedded development tools

Before compiling and flashing, please check:

- Target chip model
- Board configuration
- Pin definition
- Sensor communication interface
- Bluetooth/NFC configuration
- Sampling rate settings
- Data packet format

After compilation, flash the firmware to the SCIP hardware device.

---

### 4. Android APP

Unzip the Android application package:

```bash
unzip "SCIP APP.zip"
```

Open the project with Android Studio.

Requirements:

- Android Studio
- Android SDK
- Android device with Bluetooth support
- Android device with NFC support if NFC functions are used
- SCIP hardware device

Steps:

1. Open Android Studio.
2. Import the `SCIP APP` project.
3. Connect an Android phone.
4. Enable Bluetooth and NFC permissions.
5. Build and run the APP.
6. Connect the APP with the SCIP device.
7. Start physiological signal acquisition and monitoring.

---

## Communication

The SCIP device communicates with the Android APP mainly through wireless interfaces.

Supported communication methods may include:

- Bluetooth Low Energy
- NFC
- Serial debugging interface
- External expansion interface

The firmware packages sensor data and transmits it to the APP. The APP then parses the data packets, displays waveforms, stores data, and calculates physiological parameters.

---

## Data Processing

The system supports multiple signal processing functions, including:

- ECG waveform processing
- Heart rate calculation
- Respiratory waveform analysis
- Respiratory rate estimation
- Moving average filtering
- Calibration and smoothing
- CSV data recording
- Multi-sensor data synchronization

The exact algorithm implementation can be found in the algorithm-related modules inside the Android APP and firmware project.

---

## Application Scenarios

SCIP-system can be used in the following scenarios:

- Wearable physiological monitoring
- Real-time ECG monitoring
- Respiratory monitoring
- Portable health sensing
- Multimodal physiological signal acquisition
- Academic research and prototype validation
- Human physiological data collection
- Mobile health system development

---

## Notes

1. The hardware design should be carefully reviewed before PCB fabrication.
2. The firmware version should match the corresponding hardware version.
3. The Android APP communication protocol should be consistent with the firmware data packet format.
4. For accurate physiological monitoring, proper electrode placement, sensor attachment, and signal calibration are required.
5. This project is intended for research and development purposes. It is not a certified medical device.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Disclaimer

SCIP-system is developed for research, education, and prototype demonstration purposes. The physiological data and analysis results provided by this system should not be used as a substitute for professional medical diagnosis or treatment.

For medical or clinical use, additional hardware validation, software verification, safety evaluation, and regulatory approval are required.
