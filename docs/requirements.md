# Project Requirements

## 1. Functional Requirements

| ID | Requirement | Description | Priority |
|---|---|---|---|
| FR-01 | Image Capture | The camera captures images of the surroundings. | High |
| FR-02 | Distance Measurement | The ToF sensor measures the distance to nearby objects. | High |
| FR-03 | Obstacle Warning | The system activates vibration feedback when an obstacle meets the configured warning condition. | High |
| FR-04 | Sensor Processing | The ESP32 processes distance measurements and sensor status. | High |
| FR-05 | Wireless Communication | The ESP32 communicates relevant information to the Python backend through Wi-Fi. | High |
| FR-06 | Backend Processing | Python receives and processes sensor information and images. | High |
| FR-07 | AI Environmental Description | The backend sends images and relevant sensor information to a vision-capable AI service. | Medium |
| FR-08 | Audio Feedback | The system converts useful AI descriptions into spoken feedback. | Medium |
| FR-09 | Failure Handling | The backend handles unavailable internet connections and failed AI requests. | High |
| FR-10 | Testing and Logging | The system records relevant test results and performance measurements. | High |

## 2. Non-Functional Requirements

| ID | Requirement | Description |
|---|---|---|
| NFR-01 | Reliability | Immediate obstacle warnings should work independently of cloud connectivity. |
| NFR-02 | Responsiveness | The system should provide useful feedback without unnecessary delay. |
| NFR-03 | Maintainability | Software components should be organised into understandable modules. |
| NFR-04 | Security | API keys and credentials must not be exposed in public source code. |
| NFR-05 | Usability | Spoken descriptions should be short, clear and relevant. |
| NFR-06 | Testability | Individual components should be testable separately. |

## 3. Hardware Requirements

- ESP32-S3 Sense microcontroller.
- Camera module.
- ToF distance sensor (VL53L0X initially considered).
- Vibration motor.
- Audio output hardware or companion-device audio interface.
- Power supply.
- Wireless connectivity through a smartphone hotspot.

Final hardware selection and electrical specifications will be confirmed during implementation.

## 4. Software and Development Requirements

- Python backend.
- C/C++ embedded firmware.
- GitHub for version control and documentation.
- Webots and Wokwi for simulation.
- Autodesk Fusion for mechanical design.
- Vision-capable AI API for environmental descriptions.

## 5. Testing Requirements

The project should be evaluated through:

1. Sensor measurement tests.
2. Obstacle-warning tests.
3. Camera capture tests.
4. ESP32-to-backend communication tests.
5. AI request and response tests.
6. Audio feedback tests.
7. Internet failure and recovery tests.
8. End-to-end integration tests.

Simulation results and physical hardware test results must be documented separately.

## 6. Project Limitations

- AI descriptions depend on internet connectivity and external service availability.
- AI responses may contain errors or delays.
- Simulation cannot prove real-world sensor accuracy.
- The system is an assistive prototype and must not be presented as a guaranteed collision-prevention or navigation safety device.

## 7. Requirement Status

All requirements in this document are initial project targets. Their implementation status and measurable acceptance criteria will be updated as development progresses.
