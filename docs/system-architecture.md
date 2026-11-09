# System Architecture

## 1. Overview

The Smart Assistive Navigation Glasses are designed as a hybrid assistive system combining embedded hardware, Python-based backend processing and cloud-based artificial intelligence.

The system aims to provide immediate obstacle warnings and additional environmental descriptions for visually impaired people.

## 2. Main System Components

### 2.1 ESP32-S3 Sense

The ESP32-S3 Sense acts as the main embedded controller.

Responsibilities:
- Capture images using the camera.
- Read distance measurements from the ToF sensor.
- Process sensor readings.
- Control the vibration motor for immediate obstacle warnings.
- Communicate with the Python backend through Wi-Fi.

### 2.2 ToF Distance Sensor

The initial sensor under consideration is the VL53L0X.

Responsibilities:
- Measure the distance to nearby objects.
- Provide distance measurements to the ESP32.
- Support the immediate obstacle-warning mechanism.

The final sensor selection and measurement performance will be validated through hardware testing.

### 2.3 Vibration Warning System

The vibration motor provides immediate physical warnings when an obstacle is detected within a configured threshold.

This warning mechanism is designed to operate independently of cloud AI and internet availability.

### 2.4 Python Backend

Python will support the software integration layer.

Responsibilities:
- Receive sensor information and images.
- Process structured sensor data.
- Handle image preparation.
- Communicate with cloud AI services.
- Process AI responses.
- Support audio feedback integration.
- Record and analyse system tests.

### 2.5 Cloud-Based Vision AI

A vision-capable AI service will analyse environmental images together with relevant sensor information.

The service will return short environmental descriptions.

### 2.6 Audio Feedback

AI-generated descriptions will be converted into spoken feedback to help the user understand relevant surroundings.

## 3. System Workflow

1. The camera captures an image.
2. The ToF sensor measures nearby object distance.
3. The ESP32 processes sensor readings.
4. The local obstacle-warning mechanism activates the vibration motor when its configured condition is met.
5. Relevant image and sensor information can be transmitted to the Python backend over Wi-Fi.
6. Python prepares the information for the cloud AI service.
7. The AI analyses the submitted information.
8. Python processes the returned description.
9. The description is converted into spoken feedback.

## 4. Communication Architecture

The proposed communication path is:

ESP32-S3 Sense → Wi-Fi → Python Backend → Cloud Vision AI → Python Backend → Audio Feedback

The exact communication protocol and audio-output implementation will be finalised during development.

## 5. Development Technologies

| Component | Technology |
|---|---|
| Embedded controller | ESP32-S3 Sense |
| Embedded programming | C/C++ |
| Distance sensor | VL53L0X (initial candidate) |
| Backend programming | Python |
| AI integration | Vision-capable AI API |
| Simulation | Webots and Wokwi |
| Mechanical design | Autodesk Fusion |
| Version control | GitHub |

## 6. Reliability and Safety Considerations

- Immediate obstacle warnings must not depend on internet connectivity.
- Cloud AI responses may be delayed or unavailable.
- The system must handle communication failures.
- AI descriptions are supplementary and must not be treated as guaranteed obstacle detection.
- Sensor accuracy and system performance must be evaluated using physical hardware.
- Simulation results must be distinguished from real-world test results.

## 7. Current Development Status

This document describes the proposed system architecture. Individual components, communication protocols and integration details remain subject to implementation and testing.
