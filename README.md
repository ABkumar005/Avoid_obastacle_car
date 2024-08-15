# Arduino Motor and Servo Control with Ultrasonic Sensor
# Overview
This project utilizes an Arduino to control a pair of motors and a servo using input from an ultrasonic sensor. The ultrasonic sensor measures the distance to obstacles, and based on this distance, the motors and servo adjust the robot's direction to navigate around obstacles.

# Components Used
Arduino Board: Any Arduino board (e.g., Arduino Uno, Nano)
Ultrasonic Sensor: HC-SR04
Servo Motor: Standard servo motor
DC Motors: Two DC motors
Motor Driver: L298N or similar motor driver

# Wiring and Connectors: For connecting components
Circuit Diagram
Ultrasonic Sensor:

Trig Pin: Connected to Arduino pin 11
Echo Pin: Connected to Arduino pin 12
Servo Motor:

Control Pin: Connected to Arduino pin 3
Motors:

Right Motor:
PWM Pin: Connected to Arduino pin 5

Direction Pins: Connected to Arduino pins 7 and 8
Left Motor:
PWM Pin: Connected to Arduino pin 6
Direction Pins: Connected to Arduino pins 9 and 10
Code Explanation
Libraries
Servo.h: Controls the servo motor.
NewPing.h: Provides functionality for the ultrasonic sensor.

# Pin Definitions
SERVO_PIN: Pin connected to the servo motor.
ULTRASONIC_SENSOR_TRIG: Trigger pin for the ultrasonic sensor.
ULTRASONIC_SENSOR_ECHO: Echo pin for the ultrasonic sensor.
MAX_REGULAR_MOTOR_SPEED: Maximum speed for normal motor operation.
MAX_MOTOR_ADJUST_SPEED: Speed for adjusting motor direction when an obstacle is detected.
DISTANCE_TO_CHECK: Distance threshold for obstacle detection.
Setup Function
Initializes motor and servo pins.
Sets the initial position of the servo to 90 degrees.
Stops the motors initially.
Loop Function
Measures the distance to an obstacle using the ultrasonic sensor.
If the distance is less than the defined threshold:
Stops the motors.
Reverses the motors briefly.
Rotates the servo to check left and right distances.
Adjusts the motor direction based on the distances measured.
If no obstacle is detected within the threshold:
Moves the motors forward at a regular speed.
rotateMotor Function
Controls the direction and speed of both motors based on input values.

# Usage
Upload the Code: Load the provided Arduino code onto your Arduino board using the Arduino IDE.
Connect Components: Wire the components according to the circuit diagram.
Power the System: Ensure that the Arduino and motors are powered appropriately.
Run the Program: The robot will start moving forward and adjust its direction based on the proximity of obstacles.
Troubleshooting
Motors Not Moving: Check motor connections and ensure the motor driver is properly powered.
Servo Not Moving: Verify the control pin connection and ensure the servo is powered.
Inaccurate Distance Measurement: Ensure the ultrasonic sensor is properly aligned and free from obstructions.
References
Arduino Servo Library Documentation
NewPing Library Documentation
# License
This project is licensed under the MIT License. See the LICENSE file for details.
