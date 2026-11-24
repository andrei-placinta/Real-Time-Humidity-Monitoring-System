# Real-Time Humidity Monitoring System

An Arduino-based IoT project using **Python and serial communication** to monitor humidity sensor readings and visualize incoming data in real time.

The system receives sensor data from an Arduino board, processes the readings using Python and displays them through a continuously updated graph.

## Features

- Real-time humidity sensor data acquisition through Arduino.
- Serial communication between Arduino and Python using UART.
- Data transmission at 9600 baud.
- Serial data parsing and numerical validation.
- Real-time data visualization using Matplotlib.
- Dynamic graph updates using Drawnow.
- Rolling data window displaying the latest 40 sensor readings.
- Serial output for monitoring received sensor values.
- Arduino-side LED control based on sensor data, as described in the original project.

## Tech Stack

- **Programming Languages:** Python, Arduino
- **Hardware Platform:** Arduino
- **Serial Communication:** UART
- **Python Libraries:** PySerial, Matplotlib, Drawnow
- **Data Visualization:** Matplotlib
- **Development Environment:** Python / Arduino IDE

## Implementation Details

### Serial Communication

- Established serial communication between Arduino and Python.
- Configured the serial connection at 9600 baud.
- Received sensor readings through the serial interface.
- Parsed semicolon-separated data containing the sensor reading and two additional values.

### Data Processing

- Converted incoming sensor readings into integer values.
- Validated received values before processing.
- Handled invalid numerical input and out-of-range readings.
- Maintained a rolling window of the latest 40 measurements.

### Real-Time Data Visualization

- Used Matplotlib to display humidity sensor readings.
- Implemented dynamic graph updates using Drawnow.
- Updated the graph as new serial data became available.
- Displayed sensor measurements over successive readings.

## Project Structure

```text
humidity-monitor-main/
│
├── README.md
└── program.py
```

## Running Locally

### Requirements

- Python 3
- Arduino board
- Compatible humidity sensor
- USB connection between Arduino and computer
- Arduino firmware capable of transmitting the required serial data

### Installation

Install the required Python libraries:

```bash
pip install pyserial matplotlib drawnow
```

### Setup

1. Connect the Arduino board to your computer.

2. Upload the corresponding Arduino firmware that reads the humidity sensor and transmits the required data through serial communication.

3. Make sure the Arduino sends three semicolon-separated values per line, matching the format expected by the Python application.

4. Check the Arduino serial port. The current Python script is configured to use `COM5` at `9600` baud.

5. Run the Python application:

   ```bash
   python program.py
   ```

6. The application receives incoming sensor readings and displays them in a continuously updated graph.

## Purpose

This academic project demonstrates practical knowledge of IoT systems, Arduino integration, Python programming, serial communication, sensor data processing and real-time data visualization.
