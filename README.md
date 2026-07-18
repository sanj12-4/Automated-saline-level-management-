# Automated Saline Level Management Using IoT

## Overview

The Automated Saline Level Management System is an IoT-based healthcare monitoring solution designed to automate saline bottle supervision and reduce the risks associated with delayed bottle replacement. Traditional manual monitoring of saline levels can be time-consuming and prone to human error. This project addresses these challenges through real-time monitoring, automated alerts, and remote control capabilities.

The system uses a load cell and HX711 amplifier to continuously measure saline bottle weight, an ESP32 microcontroller for processing and communication, and MQTT protocol for real-time data transmission. When saline levels fall below predefined thresholds, the system generates alerts and automatically controls the flow using a servo motor to prevent unsafe operating conditions.

---

## Features

* Real-time saline level monitoring using load-cell sensing
* ESP32-based wireless communication
* MQTT publish-subscribe architecture
* Remote monitoring through connected devices
* Warning alert at **10 ml** saline level
* Automatic flow shutoff at **5 ml** critical level
* Servo motor-based flow control
* Buzzer-based local notification system
* Bidirectional communication for remote control and monitoring

---

## System Architecture

Load Cell → HX711 ADC → ESP32 → MQTT Broker → User Device
                                 ↓
                          Servo Motor & Buzzer

The load cell continuously measures saline bottle weight. The HX711 converts the analog signal into digital data, which is processed by the ESP32. The data is then transmitted to an MQTT broker, allowing connected devices to monitor saline levels in real time. Based on predefined thresholds, alerts are generated and the servo motor controls the saline flow.

---

## Hardware Components

| Component              | Purpose                                |
| ---------------------- | -------------------------------------- |
| ESP32                  | Main controller and communication unit |
| HX711                  | Load cell signal amplification and ADC |
| 1 kg Load Cell         | Saline weight measurement              |
| Servo Motor            | Automated flow control                 |
| Buzzer                 | Low-level alert notification           |
| Saline Bottle Assembly | Test environment                       |

---

## Software Stack

* Arduino IDE
* ESP32 Libraries
* MQTT Protocol
* Mosquitto MQTT Broker
* Embedded C/C++

---

## Working Principle

1. The load cell measures the weight of the saline bottle.
2. HX711 amplifies and digitizes the sensor signal.
3. ESP32 processes the weight data.
4. Data is published to the MQTT broker for remote monitoring.
5. A warning alert is triggered when saline level drops below 10 ml.
6. If the level reaches 5 ml, the servo motor automatically stops saline flow.
7. Users can remotely monitor and control the system through MQTT commands.

---

## Key Functionalities

### Real-Time Monitoring

The system continuously acquires and publishes saline level data, enabling timely intervention and reducing manual supervision.

### Threshold-Based Alerting

* Warning Threshold: 10 ml
* Critical Threshold: 5 ml

Alerts are generated whenever saline levels fall below these limits.

### Automated Flow Control

The servo motor automatically closes the flow path when critical levels are detected, helping prevent reverse flow and unsafe operating conditions.

### Remote Accessibility

Users can monitor saline levels and control the servo motor remotely through MQTT-based communication.

---

## Results

* Successfully monitored saline bottle levels in real time.
* Published sensor data reliably through MQTT.
* Implemented threshold-based warning and critical alerts.
* Demonstrated automatic flow shutoff using a servo motor.
* Achieved reliable bidirectional communication between ESP32 and connected devices.

---

## Future Improvements

* Design a custom PCB for compact deployment.
* Integrate cloud-based dashboards for remote analytics.
* Add battery backup for uninterrupted operation.
* Support monitoring of multiple saline bottles simultaneously.
* Implement predictive alerts using machine learning.
* Upgrade to industrial-grade sensors and actuators.



## License

This project is intended for educational and research purposes.
