🤖 Web-Controlled Surveillance Robot (Raspberry Pi & Flask)
Developed by: Aditya Mallick, Kshitij Prasad, & Sarvesh Prasad


Institution: Siksha 'O' Anusandhan (Deemed to be University) 


⭐ Project Summary
This project focuses on the design and implementation of a 

cost-effective, mobile surveillance robot controlled remotely via a web interface. Using a 


Raspberry Pi as the core controller, the system combines embedded systems, robotics, and web technologies to provide real-time video monitoring from any internet-enabled device.





The solution is highly useful for surveillance tasks in home security, industrial monitoring, and inspecting hazardous environments.




💡 Key Features & Benefits
Feature Category	Description	Source
Real-Time Monitoring	
Streams live video footage from the camera module to a web interface with minimal latency. 



Remote Control	
Allows users to control directional movement (Forward, Backward, Left, Right) from any standard web browser over Wi-Fi. 



Core Technology	
Utilizes the Raspberry Pi as the central processing unit, running a lightweight web server (Flask) for user input and streaming. 




Cost & Scalability	
Built using open-source tools and affordable components, making the design customizable and expandable for future enhancements. 



Safe Deployment	
Can be deployed in dangerous or hard-to-reach areas, reducing the need for human presence in unsafe locations. 







Export to Sheets
🏗️ System Architecture
The robot functions as an Internet of Things (IoT) device, where the Raspberry Pi manages all inputs, processing, and outputs.


The system works through the following flow:

User Input: The user sends directional commands via the Web Interface (HTML/Flask).

Control Processing: The Raspberry Pi receives the command and processes the logic in Python.


Movement: The Pi sends signals to the L298N Motor Driver, which controls the DC Motors for mobility.




Video Feed: The Raspberry Pi Camera captures real-time video, which is streamed back to the web interface using Python and the Flask framework.


🧰 Hardware & Software Requirements
Hardware Components
Component	Model/Specification	Function
Microcontroller	
Raspberry Pi 4 Model B / Pi Zero 2 W 


Central Control Unit 

Camera Module	
Raspberry Pi Camera Module v2 (8MP) 


Captures live video 

Motor Driver	
L298N Dual H-Bridge Motor Driver 

Controls motor direction and speed 

Motors	
6V Geared DC Motors with Wheels 

Provides mobility 

Power Supply	
Portable Li-ion Battery Pack 

Ensures uninterrupted, portable operation 


Export to Sheets
Software Dependencies
The core application is built using open-source Python libraries:

Library/Tool	Purpose
Python 3.x	
Primary programming language 

Flask	
Web framework for hosting the control UI and defining API endpoints 

RPi.GPIO	
Used to configure and control the Raspberry Pi's GPIO pins for motor movement 

picamera2 & OpenCV (cv2)	
Used for capturing frames and encoding them as JPEG for video streaming 

threading	
Enables concurrent execution for running the video capture loop without blocking the web server 




Export to Sheets
⚙️ Setup and Installation Guide
1. Hardware Assembly & Wiring
Assemble the chassis, mount the motors, and attach the wheels.

Connect the L298N Motor Driver outputs to the DC Motors.

Wire the L298N's input pins (E.g., 

Motor_In1 to Motor_In4) to the chosen Raspberry Pi GPIO pins (29, 31, 33, 35 are used in the main code).



Connect the Camera Module to the Pi's CSI port.

2. Software Installation (on Raspberry Pi)
Ensure you have the latest Raspberry Pi OS installed.

Install the necessary Python dependencies:

Bash

# Install the Flask web framework
pip install Flask

# Install the camera control library
pip install picamera2

# Install OpenCV for image processing (may take a while)
pip install opencv-python
Place the project files (main.py, templates/temp.html, and the static/ folder with images) into a single project directory on the Pi.

3. Running the Robot
Navigate to your project directory in the Raspberry Pi terminal.

Start the Flask server:

Bash

python main.py

(The server runs on host 0.0.0.0 and port 8080, allowing external access).

The console will display the robot's local IP address (e.g., 192.168.1.100).

On your remote Windows/Mac/Mobile device, open a web browser and enter:
http://[Your_Raspberry_Pi_IP_Address]:8080/

📝 Code Overview
The core logic resides in main.py, which integrates web routing, motor control, and video streaming.


Motor Control Functions (move_forward(), turn_left(), etc.): Directly manipulate GPIO pins 29, 31, 33, 35.



Video Threading (update_frames()): Captures camera frames asynchronously to maintain a smooth 30 FPS stream without blocking the web server.



Web Endpoints: The Flask routes define the movement commands and the video stream:

/: Serves the control panel (temp.html).


/Forward, /Backward, /left, /right, /stop: Handles POST requests from the HTML buttons to control the robot.


/video_feed: Streams the MJPEG video to the browser.

🚀 Future Enhancements
The system can be significantly improved with the following additions :

Autonomous Navigation: Integrate ultrasonic/LIDAR sensors for robust obstacle avoidance.

AI/ML Integration: Implement object detection (e.g., using Tiny-YOLO) for automatic threat recognition.

Cloud Storage: Add capabilities for storing surveillance footage on cloud platforms.

Mobile App Development: Create a dedicated mobile application for more intuitive control instead of a browser-based interface.
