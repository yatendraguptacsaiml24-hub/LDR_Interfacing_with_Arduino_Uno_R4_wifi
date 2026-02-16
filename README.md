# LDR Interfacing with Arduino Uno R4 WiFi

> A complete beginner-friendly Embedded Systems project demonstrating how to interface a **Light Dependent Resistor (LDR)** with **Arduino Uno R4 WiFi** using **PlatformIO in CLion**, and display real-time light intensity data on the Serial Monitor.

-----

## 📖 Table of Contents
1. Introduction  
2. Objective of the Project  
3. Hardware Requirements  
4. Software & Platform Details  
5. Circuit Diagram & Connections  
6. Working Principle  
7. Source Code Explanation  
8. Complete Source Code  
9. Sample Output  
10. Applications  
11. Future Improvements  
12. Author  

-----

## 🧠 1. Introduction
Light Dependent Resistor (LDR) is a commonly used sensor in embedded and IoT systems to detect ambient light levels.  
This project focuses on interfacing an **LDR sensor with Arduino Uno R4 WiFi** and converting raw analog sensor values into a **percentage-based light intensity** reading.

The project is developed using **PlatformIO** inside **CLion IDE**, which provides a professional development environment for embedded systems programming.

-----

## 🎯 2. Objective of the Project
The main objectives of this project are:
- To understand analog input reading using Arduino  
- To interface an LDR sensor with Arduino Uno R4 WiFi  
- To convert raw sensor data into meaningful output  
- To display sensor values on the Serial Monitor  
- To use PlatformIO with CLion for embedded development  

-----

## 🔧 3. Hardware Requirements
| Component | Quantity |
|---------|----------|
| Arduino Uno R4 WiFi | 1 |
| LDR (Light Dependent Resistor) | 1 |
| 10kΩ Resistor | 1 |
| Breadboard | 1 |
| Jumper Wires | As required |

-----

## 💻 4. Software & Platform Details
- **IDE Used:** CLion  
- **Embedded Platform:** PlatformIO  
- **Programming Language:** C++  
- **Framework:** Arduino Framework  
- **Board:** Arduino Uno R4 WiFi  
- **Operating System:** Windows  
- **CLion Version:** Latest stable version (exact version not specified)  
- **PlatformIO Version:** Latest stable version  

-----

## 🔌 5. Circuit Diagram & Connections
The LDR is connected using a **voltage divider circuit**.

### Connection Details:
- One terminal of **LDR → 5V**
- Other terminal of **LDR → Analog Pin A0**
- **10kΩ Resistor** connected between **A0 and GND**

This configuration allows Arduino to read variable voltage based on light intensity.

-----

## ⚙️ 6. Working Principle
- LDR resistance decreases as light intensity increases  
- Higher light → Higher voltage at A0  
- Arduino reads analog voltage (0–1023 range)  
- Raw value is mapped into **0–100%**  
- Output is printed every 500 milliseconds  

-----

## 🧩 7. Source Code Explanation
- `analogRead(A0)` reads the LDR sensor value  
- `map()` converts the raw value to percentage  
- `Serial.print()` displays values on Serial Monitor  
- `delay(500)` updates readings twice per second  

-----

## 🧪 8. Complete Source Code (main.cpp)
```cpp
#include <Arduino.h>

#define LDR_PIN A0

void setup() {
    Serial.begin(9600);
    while (!Serial);
}

void loop() {
    int ldrRaw = analogRead(LDR_PIN);

    int lightPercent = map(ldrRaw, 0, 1023, 0, 100);

    Serial.print("LDR Raw Value: ");
    Serial.print(ldrRaw);
    Serial.print(" | Light Intensity: ");
    Serial.print(lightPercent);
    Serial.println("%");

    delay(500);
}

-----

##📊 9. Sample Output (Serial Monitor)
LDR Raw Value: 215 | Light Intensity: 21%
LDR Raw Value: 678 | Light Intensity: 66%
LDR Raw Value: 945 | Light Intensity: 92%

-----
# Author -
Name : Yatendra Kumar Gupta
Gmail : guptajikrish12@gmail.com
