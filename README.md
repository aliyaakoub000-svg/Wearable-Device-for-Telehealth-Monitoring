The Fitness and Healthcare Watch Tracker is an IoT-based wearable device designed for remote real-time health monitoring. It continuously measures heart rate (BPM), oxygen saturation (SpO₂), and body temperature, transmitting the data securely to the Arduino IoT Cloud for remote access by healthcare professionals.

Features:
Real-time monitoring of BPM, SpO₂, and temperature
Cloud synchronization via MQTT using Arduino IoT Cloud
Live data visualization on a 1.28” LCD screen (GC9A01A)
Low-power IoT-enabled operation
Secure and private data handling
Potential integration for hospital systems (SQL/EDR)

Component	Description:
Arduino ESP32-S3	Microcontroller with built-in Wi-Fi and Bluetooth
MAX30102	Pulse oximeter sensor for BPM and SpO₂
LM35	Analog temperature sensor
GC9A01A 1.28” LCD	Round color display for real-time visualization
3.7V Li-ion Battery	Power source
Arduino IoT Cloud	Cloud platform for real-time monitoring and storage

Libraries Used:
#include <Wire.h>
#include "MAX30105.h"
#include <SPI.h>
#include "Adafruit_GFX.h"
#include "Adafruit_GC9A01A.h"
#include "thingProperties.h" 

How It Works:
Sensors Initialization – The MAX30102 and LM35 sensors connect via I²C and analog input.
Data Acquisition – Heart rate and temperature values are read periodically (BPM every 10ms, Temp/SpO₂ every 500ms).
Processing – The microcontroller computes BPM and SpO₂ using sensor readings.
Display – Data is shown on the round TFT LCD in real-time.
Cloud Sync – Values are uploaded to the Arduino IoT Cloud for remote access via a web dashboard or mobile app.

Communication Protocol:
Uses MQTT for efficient real-time updates between the device and the cloud, ensuring reliable data delivery even with unstable connections.

Dashboard Visualization:
BPM: Real-time graph
SpO₂: Percentage gauge
Temperature: Numeric display


Battery optimization and Bluetooth sync

Data analytics for health trend predictions
