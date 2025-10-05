🛰️ Development of a Web-Controlled Surveillance Robot Using Raspberry Pi for Real-Time Monitoring
📘 Overview

This project demonstrates the design and implementation of a web-controlled surveillance robot powered by a Raspberry Pi.
It allows real-time video streaming and remote movement control through a simple web interface.
Users can monitor their surroundings from any internet-enabled device, making it a cost-effective solution for home, industrial, or educational surveillance.

⚙️ Features

📹 Real-time video streaming via Flask and OpenCV

🌐 Web-based control interface (Forward, Backward, Left, Right, Stop)

📡 Wi-Fi-enabled remote operation using Raspberry Pi

🔋 Portable and low-power design

🧩 Open-source and customizable for future upgrades (e.g., sensors, AI, obstacle avoidance)

🧠 Technologies Used

Hardware

Raspberry Pi (Zero 2W / 4 Model B)

Raspberry Pi Camera Module / USB Webcam

L298N Motor Driver

DC Motors with Wheels

Battery Pack or Power Bank

Chassis with Wi-Fi connectivity

Software

Python (Flask, OpenCV, RPi.GPIO, picamera2)

Thonny IDE / Raspberry Pi OS

HTML for Web UI

🧩 System Architecture

Camera Module captures live video.

Raspberry Pi hosts a Flask server for:

Streaming the video feed

Receiving movement commands

Motor Driver (L298N) executes commands from the Pi via GPIO pins.

Web Interface allows remote control and live monitoring.

🚀 How to Run

Set up hardware:

Connect camera and motor driver to Raspberry Pi.

Wire the motors as per the circuit diagram.

Install required libraries:

pip install flask opencv-python RPi.GPIO picamera2


Run the Flask app:

python main.py


Access the robot’s web interface:

Open a browser and go to:
http://<your_raspberrypi_ip>:8080

Use the on-screen buttons to control movement and view live video.

🧪 Testing and Results

The robot successfully:

Streamed real-time video with minimal latency

Responded to web commands instantly

Operated smoothly within Wi-Fi range

Verified in indoor and outdoor environments for connectivity and responsiveness.

⚠️ Limitations

No obstacle avoidance or AI-based detection

Operates only within Wi-Fi range

Limited battery backup

Manual control only (non-autonomous)

🔮 Future Enhancements

Add AI-based object detection and autonomous navigation

Integrate ultrasonic sensors for obstacle avoidance

Implement mobile app and cloud-based storage for video

Enable night vision and long-range communication

👨‍💻 Team Members
Name	Roll No.	Contribution
Aditya Mallick	2341013087	Software Design, Planning, Testing
Kshitij Prasad	2341016424	Hardware Design, Assembly
Sarvesh Prasad	2341016425	Documentation, Integration
📚 References

OpenCV Documentation

Flask Official Docs

Raspberry Pi Blog

MQTT IoT Protocol
