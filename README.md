# Smart-Predictive-Solar-Street-Lighting-System
An ESP32-based solar street lighting prototype with adaptive brightness and a predictive multi-pole lighting concept.

📌 **About the Project**
Conventional street lighting systems frequently operate at maximum brightness throughout the night, regardless of whether vehicles or pedestrians are present. This constant operation leads to substantial, unnecessary energy loss.

To solve this, this project introduces an intelligent, solar-powered street light system that dynamically regulates its brightness according to surrounding light levels and real-time motion detection. Built using an ESP32 microcontroller, the framework can be expanded across a networked network of lighting poles that communicate seamlessly.

The primary objective is to generate a predictive "wave" of light along the roadway, ensuring that upcoming lighting zones illuminate proactively as a traveler advances down the path.
Here is a refined version of the **Problem Statement** section that maintains your exact core message while improving its structure and technical tone:

 🎯 **Problem Statement**

Standard street lighting infrastructure consumes electricity continuously, running at full power even on completely deserted roadways. This practice results in significant energy waste and higher operational costs.

Project Objectives:

* Maintain low standby lighting when roads are idle to save energy.
* Ramp up to full brightness instantly whenever motion is detected.
* Leverage solar energy and battery storage for self-sustaining off-grid operation.
* Establish an interconnected multi-pole concept that illuminates upcoming road segments ahead of moving subjects.
How It Works
System Components:

PIR Sensor → Senses real-time movement

LDR Sensor → Measures ambient light levels

ESP32 → Acts as the central processing unit

LED Unit → Simulates the street light fixture

MOSFET → Regulates power switching and PWM brightness

Basic Operational Flow:
🌙 Night / Low Ambient Light
          ↓
    Low Brightness (Standby)
          ↓
    Motion Detected
          ↓
    High Brightness (Active)
          ↓
    Motion Ends
          ↓
    Countdown Timeout
          ↓
    Low Brightness (Standby)
    
The multi-pole version is designed so that information from one lighting zone can be used to activate the next lighting zone, creating a predictive wave of light.
✨ Key Features

☀️ Solar-Powered Concept
🔋 Battery Energy Storage
💡 Adaptive LED Brightness
🚶 PIR Motion Detection
🌙 LDR Ambient Sensing
🎛️ ESP32 Microcontroller Control
🛣️ Predictive Multi-Pole Concept
⚡ Energy-Efficient Operation
🔌 Embedded Logic System

🔧 Hardware Components
Component	Purpose
ESP32-WROOM-32	Main controller
HC-SR501 PIR	Motion detection
LDR + LM393	Ambient light detection
LED	Street-light simulation
IRLZ44N MOSFET	LED switching/control
MT3608	Boost converter
18650 Li-ion battery	Energy storage
Solar panel	Solar energy generation
Solar charge controller	Battery charging
220Ω resistor	LED current limiting

📍 Prototype Pin Configuration
Component	ESP32 Pin
PIR Sensor	GPIO 27
LDR	GPIO 34
LED / MOSFET Control	GPIO 25

⚙️ Prototype Working
The prototype was tested using a three-pole lighting setup controlled by an ESP32.

The demonstrated brightness behavior was:

No Motion
   ↓
~35% Brightness

Motion Detected
   ↓
100% Brightness

Motion Ends
   ↓
Timeout
   ↓
~35% Brightness
The brightness levels and timeout can be modified in the Arduino code.

 Working Principle

1. The **LDR** checks the surrounding ambient light.
2. During daylight, the street lights remain OFF.
3. During low-light/night conditions, the system enables the lighting system.
4. The lights operate at approximately **35% brightness** when there is no detected movement.
5. When the **PIR sensor detects motion**, the brightness increases to approximately **100%**.
6. After movement stops, the system waits for a predefined timeout.
7. The brightness then returns to the lower level.

The brightness levels and timeout duration can be modified in the Arduino code.

🔋 Solar Power Architecture

The solar power flow of the prototype can be represented as:


              ☀️ Solar Panel
                    ↓
          🔋 Solar Charge Controller
                    ↓
             🔋 18650 Battery
                    ↓
             ⚡ Boost Converter
                    ↓
               🧠 ESP32
                    ↓
              💡 LED Lighting

The solar panel provides energy to the charging system, which stores energy in the battery.

The stored energy is then supplied to the electronics and lighting system through the required power-conversion stages.


🔌 System Circuit / Block Diagram

The following diagram represents the main hardware architecture and connections of the **Smart Predictive Solar Street Lighting System**.


 🧠 Predictive Multi-Pole Concept

The major concept of this project is to coordinate multiple street-light poles according to the direction of movement.

 Three-Pole Concept


       POLE 1          POLE 2          POLE 3

        💡              💡              💡
        │               │               │
       PIR             PIR             PIR
        │               │               │
        └───────►───────┴───────►───────┘
                 Movement Direction →


When movement is detected at one lighting zone, the next lighting zone can be prepared to provide illumination ahead of the moving person or vehicle.

### Current Prototype

The current prototype demonstrates the lighting-control concept using a **centralized ESP32**.

### Future Version

A future implementation can use:

* Individual controllers for each pole
* Wireless communication between poles
* Movement-direction detection
* Predictive activation of upcoming lights
* Coordinated brightness control

This can create a **predictive wave of illumination** along the road.


 📊 Expected Benefits

The proposed system can provide the following benefits:

* ⚡ Reduced unnecessary lighting energy consumption
* 🔋 Better utilization of stored solar energy
* 💡 Improved illumination around moving objects
* 🛣️ Suitable for low-traffic roads
* ☀️ Reduced dependence on grid electricity
* 🌱 Environment-friendly lighting approach
* 📈 Scalable multi-pole architecture
* 💰 Potential reduction in operating costs


 🚀 Future Improvements

Future versions of the project could include:

* 📡 Wireless communication between lighting poles
* 🔋 Improved battery management system
* ☀️ MPPT-based solar charging
* 💡 High-power LED street-light modules
* ⚡ Dedicated constant-current LED driver
* 💤 ESP32 deep-sleep power management
* 📊 Real-time energy-consumption monitoring
* 🤖 Vehicle/person classification
* 🌐 IoT-based remote monitoring
* 🧠 Advanced predictive movement detection
* 📍 Direction and speed estimation
* 📱 Mobile application for system monitoring

 🛣️ Potential Applications

The system can be adapted for:

* 🏘️ Rural roads
* 🏡 Village streets
* 🌾 Agricultural roads
* 🎓 College campuses
* 🏭 Industrial areas
* 🛣️ Low-traffic roads
* 🌄 Remote locations
* ☀️ Solar-powered infrastructure
* 🏕️ Public pathways and isolated areas


