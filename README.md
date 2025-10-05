# 🤖 Web-Controlled Surveillance Robot Using Raspberry Pi

## Project Overview

[cite_start]This project details the design and implementation of a **Web-Controlled Surveillance Robot** powered by a **Raspberry Pi** for **real-time remote monitoring**[cite: 17]. [cite_start]The system allows a user to remotely control the robot's movement (forward, backward, left, right) and receive a live video feed via a standard web browser on any internet-enabled device[cite: 18, 89].

[cite_start]The robot functions as an **IoT-enabled device** [cite: 206][cite_start], combining a mobile platform, a camera module, and a lightweight web server (Flask) hosted on the Raspberry Pi[cite: 20]. [cite_start]This makes it a cost-effective, flexible solution suitable for applications in home security, industrial surveillance, and monitoring hazardous environments[cite: 23, 92].

---

## ✨ Key Features

* [cite_start]**Real-Time Remote Monitoring:** Stream live video footage from the robot's camera to a web-based interface[cite: 18, 168].
* [cite_start]**Web-Based Control:** Control the robot's directional movement (forward, backward, left, right) remotely using buttons on a simple web GUI[cite: 109, 124].
* [cite_start]**Cost-Effective Design:** Utilizes affordable hardware components like the Raspberry Pi Zero 2 W and open-source software (Python, Flask, OpenCV)[cite: 23, 170].
* [cite_start]**Wireless Communication:** Uses **Wi-Fi** for real-time data transmission and control over a local network or the internet[cite: 110, 315].
* [cite_start]**Scalable Architecture:** Built with modular components, allowing for future enhancements such as object detection or autonomous navigation [cite: 175, 467-468].

---

## 💻 Technologies Used

| Category | Component / Library | Purpose |
| :--- | :--- | :--- |
| **Core Controller** | [cite_start]Raspberry Pi 4 Model B / Raspberry Pi Zero 2 W [cite: 338, 391, 645] | [cite_start]Central Processing Unit (CPU) for control, communication, and video processing [cite: 90] |
| **Programming Language** | Python | [cite_start]Main programming language used for motor control and web server logic [cite: 111, 398] |
| **Web Framework** | **Flask** | [cite_start]Lightweight web framework to host the control interface and handle streaming [cite: 111, 625] |
| **Video Streaming** | `picamera2`, `cv2` (OpenCV) | [cite_start]Captures video frames and encodes them as JPEG for web streaming [cite: 630-631] |
| **Motor Control** | `RPi.GPIO` | [cite_start]Controls the GPIO pins on the Raspberry Pi to manipulate the motors [cite: 632] |
| **Motor Driver** | [cite_start]L298N Dual H-Bridge [cite: 358] | [cite_start]Interfaces with the Raspberry Pi to control the DC motors [cite: 360] |
| **Communication** | Wi-Fi (built-in) | [cite_start]Provides wireless connectivity for remote control and video streaming [cite: 369] |

---

## 🛠️ Hardware Requirements

[cite_start]The components below were used for this project[cite: 391, 645]:

| Component | Specification | Quantity |
| :--- | :--- | :--- |
| **Microcontroller** | [cite_start]Raspberry Pi Zero 2 W (or Raspberry Pi 4 Model B) [cite: 645, 338] | 1 |
| **Camera Module** | [cite_start]Raspberry Pi Camera Module v2 [cite: 347] | 1 |
| **Motor Driver** | [cite_start]L298N Dual H-Bridge Motor Driver [cite: 358, 645] | 1 |
| **Motors + Wheels** | [cite_start]DC Geared Motors (e.g., 100 RPM) with Rubber Wheels [cite: 362, 645] | 4 |
| **Chassis** | [cite_start]4-wheel acrylic chassis [cite: 647] | 1 set |
| **Power Supply** | [cite_start]Power Bank/Battery Pack (5V for Pi, 12V for Motors) [cite: 651] | 1 |
| **Storage** | [cite_start]MicroSD Card (Class 10, 16GB+) [cite: 371] | 1 |
| **Miscellaneous** | [cite_start]Jumper Wires & Connectors [cite: 656] | - |

---

## 🚀 Setup and Installation

### 1. Hardware Assembly

1.  [cite_start]**Mount Components:** Assemble the motors, wheels, and Raspberry Pi/Camera Module onto the chassis [cite: 119-121].
2.  [cite_start]**Motor Driver Connection:** Connect the **L298N Motor Driver** to the DC Motors[cite: 358].
3.  [cite_start]**Raspberry Pi Interfacing:** Connect the motor driver's control pins to the designated **GPIO pins** on the Raspberry Pi[cite: 360, 519]. [cite_start]The GPIO pins used in the code are **29, 31, 33, and 35** for `Motor_In1` through `Motor_In4` respectively[cite: 519].
4.  [cite_start]**Camera Connection:** Connect the Pi Camera Module to the Raspberry Pi's CSI port[cite: 19].
5.  [cite_start]**Power:** Connect the power supply to both the Raspberry Pi and the motor driver (ensure correct voltage for each)[cite: 377].

### 2. Software Configuration

1.  [cite_start]**OS and Libraries:** Install the Raspberry Pi OS on the MicroSD card[cite: 372].
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
    python main_code_file_name.py
    ```

3.  [cite_start]The script will start the **Flask web server** on port `8080` [cite: 622] and print the robot's local IP address (e.g., `192.168.x.x:8080`).
4.  Open a web browser on a device connected to the **same Wi-Fi network** as the robot and enter the printed IP address (e.g., `http://192.168.x.x:8080`).
5.  [cite_start]The web interface will load, allowing you to view the live stream and control the robot's movement[cite: 109, 163].

---

## 💡 Future Scope and Enhancements

The current project is a robust foundation for a surveillance system. [cite_start]Future development could include [cite: 466-472]:

* [cite_start]**Autonomous Navigation:** Integrate **advanced sensors** (ultrasonic, LIDAR) for obstacle avoidance and implement basic autonomous navigation capabilities[cite: 467].
* [cite_start]**AI/ML Integration:** Implement **AI-based algorithms** for features like object detection, facial recognition, or automatic threat recognition[cite: 468].
* [cite_start]**Extended Range:** Incorporate **cellular communication** (3G/4G/5G) for remote operation beyond the local Wi-Fi range[cite: 317, 319].
* [cite_start]**Power Optimization:** Enhance the power management system with higher capacity batteries or solar charging for prolonged operation[cite: 469].
* [cite_start]**Cloud Services:** Add support for **cloud storage** and data analytics for surveillance footage[cite: 472].
