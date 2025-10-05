# 🤖 Web-Controlled Surveillance Robot Using Raspberry Pi

## Project Overview

This project details the design and implementation of a **Web-Controlled Surveillance Robot** powered by a **Raspberry Pi** for **real-time remote monitoring**. The system allows a user to remotely control the robot's movement (forward, backward, left, right) and receive a live video feed via a standard web browser on any internet-enabled device.

The robot functions as an **IoT-enabled device**, combining a mobile platform, a camera module, and a lightweight web server (Flask) hosted on the Raspberry Pi. This makes it a cost-effective, flexible solution suitable for applications in home security, industrial surveillance, and monitoring hazardous environments.

---

## ✨ Key Features

* **Real-Time Remote Monitoring:** Stream live video footage from the robot's camera to a web-based interface.
* **Web-Based Control:** Control the robot's directional movement (forward, backward, left, right) remotely using buttons on a simple web GUI.
* **Cost-Effective Design:** Utilizes affordable hardware components like the Raspberry Pi Zero 2 W and open-source software (Python, Flask, OpenCV).
* **Wireless Communication:** Uses **Wi-Fi** for real-time data transmission and control over a local network or the internet.
* **Scalable Architecture:** Built with modular components, allowing for future enhancements such as object detection or autonomous navigation.

---

## 💻 Technologies Used

| Category | Component / Library | Purpose |
| :--- | :--- | :--- |
| **Core Controller** | Raspberry Pi 4 Model B / Raspberry Pi Zero 2 W | Central Processing Unit (CPU) for control, communication, and video processing |
| **Programming Language** | Python | Main programming language used for motor control and web server logic |
| **Web Framework** | **Flask** | Lightweight web framework to host the control interface and handle streaming |
| **Video Streaming** | `picamera2`, `cv2` (OpenCV) | Captures video frames and encodes them as JPEG for web streaming |
| **Motor Control** | `RPi.GPIO` | Controls the GPIO pins on the Raspberry Pi to manipulate the motors |
| **Motor Driver** | L298N Dual H-Bridge | Interfaces with the Raspberry Pi to control the DC motors |
| **Communication** | Wi-Fi (built-in) | Provides wireless connectivity for remote control and video streaming |

---

## 🛠️ Hardware Requirements

The components below were used for this project:

| Component | Specification | Quantity |
| :--- | :--- | :--- |
| **Microcontroller** | Raspberry Pi Zero 2 W (or Raspberry Pi 4 Model B) | 1 |
| **Camera Module** | Raspberry Pi Camera Module v2 | 1 |
| **Motor Driver** | L298N Dual H-Bridge Motor Driver | 1 |
| **Motors + Wheels** | DC Geared Motors (e.g., 100 RPM) with Rubber Wheels | 4 |
| **Chassis** | 4-wheel acrylic chassis | 1 set |
| **Power Supply** | Power Bank/Battery Pack (5V for Pi, 12V for Motors) | 1 |
| **Storage** | MicroSD Card (Class 10, 16GB+) | 1 |
| **Miscellaneous** | Jumper Wires & Connectors | - |

---

## 🚀 Setup and Installation

### 1. Hardware Assembly

1.  **Mount Components:** Assemble the motors, wheels, and Raspberry Pi/Camera Module onto the chassis.
2.  **Motor Driver Connection:** Connect the **L298N Motor Driver** to the DC Motors.
3.  **Raspberry Pi Interfacing:** Connect the motor driver's control pins to the designated **GPIO pins** on the Raspberry Pi. The GPIO pins used in the code are **29, 31, 33, and 35** for `Motor_In1` through `Motor_In4` respectively.
4.  **Camera Connection:** Connect the Pi Camera Module to the Raspberry Pi's CSI port.
5.  **Power:** Connect the power supply to both the Raspberry Pi and the motor driver (ensure correct voltage for each).

### 2. Software Configuration

1.  **OS and Libraries:** Install the Raspberry Pi OS on the MicroSD card.
2.  **Dependencies:** Install the required Python libraries on the Raspberry Pi using the terminal:

    ```bash
    # Install Flask
    pip install Flask

    # Install OpenCV for video processing
    # Use the appropriate command for your RPi OS version
    pip install opencv-python

    # Install the camera control library
    pip install picamera2
    ```

3.  **Code Transfer:** Upload the project code (specifically the `main` script and the `temp.html` template for the web interface) to the Raspberry Pi.

### 3. Running the System

1.  Navigate to the directory containing the main Python script.
2.  Execute the script using:

    ```bash
    python main.py
    ```

3.  The script will start the **Flask web server** on port `8080` and print the robot's local IP address (e.g., `192.168.x.x:8080`).
4.  Open a web browser on a device connected to the **same Wi-Fi network** as the robot and enter the printed IP address (e.g., `http://192.168.x.x:8080`).
5.  The web interface will load, allowing you to view the live stream and control the robot's movement.

---

## 💡 Future Scope and Enhancements

The current project is a robust foundation for a surveillance system. Future development could include:

* **Autonomous Navigation:** Integrate **advanced sensors** (ultrasonic, LIDAR) for obstacle avoidance and implement basic autonomous navigation capabilities.
* **AI/ML Integration:** Implement **AI-based algorithms** for features like object detection, facial recognition, or automatic threat recognition.
* **Extended Range:** Incorporate **cellular communication** (3G/4G/5G) for remote operation beyond the local Wi-Fi range.
* **Power Optimization:** Enhance the power management system with higher capacity batteries or solar charging for prolonged operation.
* **Cloud Services:** Add support for **cloud storage** and data analytics for surveillance footage.

**Developed by:** Aditya Mallick, Kshitij Prasad, & Sarvesh Prasad 
