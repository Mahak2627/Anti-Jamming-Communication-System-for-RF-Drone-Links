# Anti-Jamming-Communication-System-for-RF-Drone-Links
Real-time RF jamming detection and automatic recovery using ESP32 and machine learning.
Minor Project, NIT Jalandhar (2025-26)

## Problem
Drones depend on RF links that can be disrupted by jamming. This project detects
jamming quickly and restores communication without human input.

## How it works
1. **Sense:** The receiver logs RSSI, SNR and packet delivery ratio (PDR).
2. **Detect:** An ML model classifies the link as Normal, Constant, Random or Sweep jamming.
3. **Act:** Both nodes hop to a clean channel and the link recovers.


## Hardware
- 2x ESP32 dev boards
- OLED display / RGB LEDs (Green = normal, Yellow = jammed, Blue = recovered)
- Laptop running the ML script

## Software
- Python (scikit-learn / TensorFlow), ESP32 firmware (Arduino/ESP-IDF)
- MATLAB/Simulink (quadrotor hover model with PID control)

## Repo structure
- `firmware/`  ESP32 Tx/Rx code
- `ml/`        data collection, training, real-time detection
- `simulink/`  drone model
- `docs/`      diagrams, screenshots, demo



Lab test: jammer on caused 78% packet loss (ping test) before mitigation.

## Demo


## How to run
1. Flash `firmware/` to both ESP32 boards
2. `pip install -r requirements.txt`
3. `python ml/detect.py`

## Safety note
All tests were done in a controlled lab setup with college-provided equipment.
Do not use jamming devices outside authorized environments.

## Future work
- Handle adversaries that vary jamming power
- GPS-free localisation and cooperative retreat
- Reinforcement learning (Q-learning/DQN) for channel selection

## Author
Mahak | NIT Jalandhar 
