# ESP32-S3 DHT20 MQTT Telemetry to CoreIoT

This project implements a complete IoT system using the ESP32-S3 to collect temperature and humidity data from a DHT20 sensor and transmit the measurements to the CoreIoT cloud platform using the MQTT protocol. The received telemetry is stored and visualized in real time through an interactive dashboard.

## Overview

In modern IoT systems, collecting sensor data and sending it to a cloud platform is a fundamental task. This project demonstrates the entire end-to-end pipeline, including:

- Reading temperature and humidity data from the DHT20 sensor via the I2C interface.
- Connecting the ESP32-S3 to a WiFi network.
- Packaging sensor readings into JSON telemetry messages.
- Publishing telemetry to the CoreIoT platform using MQTT.
- Monitoring real-time data through the CoreIoT dashboard.

System pipeline:

```text
DHT20 → ESP32-S3 → WiFi → MQTT → CoreIoT → Real-time Dashboard
```

---

## System Objectives

The main objectives of this project are:

- Read temperature and humidity data from the DHT20 sensor.
- Connect the ESP32-S3 to a WiFi network.
- Establish MQTT communication with the CoreIoT platform.
- Periodically publish telemetry data to the cloud.
- Visualize live sensor data on the CoreIoT dashboard.

---

## Hardware Requirements

- ESP32-S3 YoloUno Development Board
- DHT20 Temperature and Humidity Sensor
- Jumper wires
- USB-C cable

---

## Software Requirements

- Visual Studio Code
- PlatformIO Extension
- CoreIoT account
- MQTT broker provided by CoreIoT

---

## Hardware Connection

### DHT20 to ESP32-S3 Wiring

| DHT20 Pin | ESP32-S3 Pin | Description |
|----------|-------------|-------------|
| VCC | 3.3V | Power supply |
| GND | GND | Ground |
| SDA | GPIO8 | I2C data line |
| SCL | GPIO9 | I2C clock line |

> Note: The GPIO pins may vary depending on your firmware configuration.

---

## Input and Output

### Input

The input consists of temperature and humidity measurements captured by the DHT20 sensor.

Example sensor readings:

```text
Temperature: 29.4 °C
Humidity: 68.2 %
```

### Output

The ESP32-S3 publishes the measurements to CoreIoT as JSON telemetry.

Example payload:

```json
{
  "temperature": 29.4,
  "humidity": 68.2
}
```

The CoreIoT dashboard displays the data in real time.

---

## Data Flow

```text
DHT20 → ESP32-S3 → WiFi → MQTT → CoreIoT → Real-time Dashboard
```

---

## Dashboard Preview

![CoreIoT Dashboard](dashboard.png)

---

## How It Works

1. The ESP32-S3 initializes the I2C interface.
2. Temperature and humidity data are read from the DHT20 sensor.
3. The board connects to a WiFi network.
4. An MQTT connection to CoreIoT is established.
5. Sensor readings are formatted as JSON telemetry.
6. Data is published periodically.
7. The CoreIoT dashboard updates automatically.

---
