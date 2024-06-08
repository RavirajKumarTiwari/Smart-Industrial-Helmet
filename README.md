# IoT-Based Smart Industrial Helmet

## Overview

This project is an IoT-based Smart Industrial Helmet designed to monitor environmental conditions and worker safety in industrial environments. The helmet is equipped with sensors to measure temperature, humidity, and gas levels, as well as a fall detection mechanism. It provides real-time data logging and alerting through a cloud platform, ensuring timely responses to hazardous conditions.

![Project prototype](/img/project%20pic.jpg)

## Features

- **Environmental Monitoring**: Measures temperature, humidity, and gas levels.
- **Fall Detection**: Detects falls and sends alerts.
- **Real-Time Data Logging**: Uses ThingSpeak to log data in real-time.
- **Visual and Audio Alerts**: Includes LEDs and a buzzer to alert workers of hazardous conditions.
- **WiFi Connectivity**: Uses NodeMCU ESP8266 for wireless data transmission.

## Components

- **Arduino Uno**: Main microcontroller.
- **NodeMCU ESP8266**: WiFi module for cloud connectivity.
- **DHT11 Sensor**: Measures temperature and humidity.
- **MPU6050 Sensor**: Measures accelerometer and gyroscope data for fall detection.
- **MQ2 Gas Sensor**: Detects gas levels.
- **I2C LCD Display**: Displays sensor readings.
- **Buzzer**: Provides audio alerts.
- **LEDs**: Indicate system status and alerts.

## Circuit Diagram

![Circuit Diagram](/img/Schematic_smart-helmet_2024-05-26.png)

## Prerequisites

- Arduino IDE
- Libraries: `Wire`, `LiquidCrystal_I2C`, `MPU6050`, `DHT`
- ThingSpeak account

## Setup

### Arduino Uno

1. **Wiring**:
   - **DHT11 Sensor**: Data pin to Digital Pin 7.
   - **MPU6050 Sensor**: Connect to SDA and SCL pins.
   - **MQ2 Gas Sensor**: Data pin to Analog Pin A1.
   - **Buzzer**: Positive pin to Digital Pin 8.
   - **I2C LCD Display**: SDA to A4, SCL to A5, 5V, GND.
   - **LEDs**: Connect to Digital Pins 9, 10, 11 for temperature, data transmission, and gas alerts respectively.

2. **Upload Code**:
   - Open the Arduino IDE.
   - Load the `ArduinoUnoCode.ino` file.
   - Select the correct board and port.
   - Upload the code.

### NodeMCU ESP8266

1. **WiFi Configuration**:
   - Open the `NodeMCUCode.ino` file.
   - Update the SSID and Password for your WiFi network.

2. **ThingSpeak Configuration**:
   - Update the `apiKey` with your ThingSpeak Write API Key.

3. **Upload Code**:
   - Select the correct board (NodeMCU 1.0) and port in the Arduino IDE.
   - Upload the code.

## Usage

1. **Power On**: Connect the Arduino and NodeMCU to a power source.
2. **Initialization**: The LCD will display sensor initialization.
3. **Data Logging**: Sensor data will be logged to ThingSpeak.
4. **Alerts**: LEDs and buzzer will alert if abnormal conditions are detected (high temperature, gas leak, or fall).

## Results and Iterations

- **Initial Testing**: Verified sensor readings and data transmission.
- **Fall Detection**: Fine-tuned the MPU6050 threshold values for accurate fall detection.
- **Real-Time Monitoring**: Successfully logged data to ThingSpeak and set up triggers for alerts.
- **Improved Alert System**: Enhanced the LED and buzzer alerts based on feedback from initial tests.
- **Sensor Calibration**: Adjusted sensor calibration for more accurate readings.

## Prototyping and Testing

The prototype was developed using Arduino Uno and NodeMCU ESP8266, integrating various sensors. The system was tested under different environmental conditions to ensure reliability. The fall detection feature was specifically tested by simulating falls to adjust sensitivity.
![Testing](/img/underProcess%20Project%20pic.jpg)

## Cloud Platform or Server Configuration

ThingSpeak was chosen for its ease of integration with IoT projects and real-time data visualization capabilities. The ThingSpeak channel was configured to log data from the sensors and set up alerts for abnormal conditions. The NodeMCU ESP8266 handles the WiFi connectivity and data transmission to ThingSpeak.

### Sensors data on ThingSpeak

![Humidity Sensor Data](/img/Screenshot%202024-05-26%20145535.png)
![Gas Sensor Data](/img/Screenshot%202024-05-26%20145625.png)
![Fall Sensor Data](/img/Screenshot%202024-05-26%20145649.png)
![Temperature Sensor Data](/img/temp%20data.png)

## Acknowledgments

- [Electronics Cats](https://github.com/ElectronicCats) for providing the MPU6050 library.
- [Adafruit](https://github.com/adafruit) for providing the DHT sensor library.
- [ThingSpeak](https://thingspeak.com/) for their IoT platform.
