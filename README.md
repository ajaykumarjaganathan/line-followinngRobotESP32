**🚗 Smart Adaptive PID Line Following Robot with Obstacle Intelligence 🤖**
📌 Project Overview

This project implements a PID-based autonomous line-following robot using an Arduino Nano.
Unlike traditional line followers that rely on simple conditional logic, this system uses closed-loop PID control to ensure smooth, stable, and adaptive navigation.

Additionally, the robot integrates ultrasonic obstacle detection, enabling intelligent environmental awareness.

🧠 Key Features

✅ PID-based smooth line tracking

✅ Adaptive speed control on curves

✅ Ultrasonic obstacle detection

✅ Dynamic motor speed correction

✅ LED status indicators

✅ Junction detection capability

✅ Expandable architecture

🔧 Hardware Components

Arduino Nano (ATmega328P)

IR Line Tracking Sensors (2/3/5 array)

L298N Motor Driver Module

DC Motors + Chassis

HC-SR04 Ultrasonic Sensor

Li-ion Battery (7.4V recommended)

LEDs (Status indicators)

Buzzer (Optional)

🔍 System Architecture
IR Sensors → Arduino Nano → PID Algorithm → L298N → Motors
Ultrasonic Sensor → Arduino Nano → Obstacle Logic
Battery → Motor Driver + Arduino
⚙️ Working Principle
1️⃣ Line Detection

IR sensors detect contrast between black line and white surface.

Black surface → Low reflection

White surface → High reflection

Sensor data is converted into a positional error value.

2️⃣ PID Control Logic

The correction value is calculated using:

𝑂
𝑢
𝑡
𝑝
𝑢
𝑡
=
(
𝐾
𝑝
×
𝑒
𝑟
𝑟
𝑜
𝑟
)
+
(
𝐾
𝑖
×
𝑖
𝑛
𝑡
𝑒
𝑔
𝑟
𝑎
𝑙
)
+
(
𝐾
𝑑
×
𝑑
𝑒
𝑟
𝑖
𝑣
𝑎
𝑡
𝑖
𝑣
𝑒
)
Output=(Kp×error)+(Ki×integral)+(Kd×derivative)

Motor speeds are dynamically adjusted:

Left Motor Speed  = Base Speed - Correction
Right Motor Speed = Base Speed + Correction

This ensures:

Smooth turns

Reduced oscillation

Faster response

3️⃣ Adaptive Speed Mechanism

The robot reduces speed on curves:

baseSpeed = MAX_SPEED - abs(error) * factor;

This increases stability during sharp turns.

4️⃣ Obstacle Intelligence

The ultrasonic sensor continuously measures distance:

𝐷
𝑖
𝑠
𝑡
𝑎
𝑛
𝑐
𝑒
=
(
𝑇
𝑖
𝑚
𝑒
×
0.034
)
/
2
Distance=(Time×0.034)/2

If obstacle distance < threshold:

Robot stops

Optional rerouting logic executes

📊 Control Flow
Start
 ↓
Read Ultrasonic Sensor
 ↓
If Obstacle → Stop / Avoid
Else
 ↓
Read IR Sensors
 ↓
Calculate Error
 ↓
Compute PID Output
 ↓
Adjust Motor Speed
 ↓
Repeat Loop
🔢 Example PID Parameters
Kp = 20;
Ki = 0;
Kd = 8;

Note: PID values must be tuned based on track conditions.

🚀 Advantages Over Traditional Line Followers
Traditional	This Project
Binary logic	Closed-loop control
Jerky motion	Smooth tracking
Constant speed	Adaptive speed
No intelligence	Obstacle-aware
📸 Hardware Images

(Add your real images here)

Chassis setup

Sensor mounting

Wiring connections

Final robot view

🔌 Wiring Overview
Component	Arduino Pin
IR Left	D2
IR Right	D3
Ultrasonic TRIG	D8
Ultrasonic ECHO	D9
L298N IN1	D4
L298N IN2	D5
L298N IN3	D6
L298N IN4	D7
🛠 Future Enhancements

Bluetooth control mode

OLED live diagnostics display

Maze-solving algorithm

AI-based vision tracking

PID auto-tuning

🎯 Applications

Warehouse automation

Industrial transport systems

Smart logistics

Educational robotics

Autonomous navigation research

📚 Technical Concepts Used

Closed-loop control system

PID algorithm

PWM motor speed control

Ultrasonic ranging

Embedded C (Arduino)

📌 Author

AJAYKUMAR JAGANATHAN  | 
Artificial Intelligence & Data Science Student

📜 License

This project is open-source and available under the MIT License.
