# IoT-Based Water Level Monitoring System

A smart **IoT water level monitoring device** using ESP8266 and the **Blynk IoT platform** for real-time tank level visualization, automated alerts, and motor control.

---

## 🌟 Features

- Real-time water level monitoring with an **ultrasonic sensor**.  
- Live data visualization on **Blynk mobile app** (New Blynk).  
- Interactive **motor control** using a relay via the Blynk interface.  
- LED indicators to show water levels: Very Low, Low, Medium, High, Full.  
- Configurable tank capacity and thresholds for custom tanks.  
- LCD display for local monitoring.

---

## 🔧 Hardware Components

| Component | Description |
|-----------|-------------|
| ESP8266 NodeMCU | Microcontroller for IoT connectivity |
| Ultrasonic Sensor (HC-SR04) | Measures water level distance |
| Relay Module | Controls motor pump |
| 16x2 I2C LCD | Displays water level locally |
| LEDs (5x) | Indicates water level ranges |
| Connecting Wires | For hardware connections |

---

## 💻 Software / Libraries

- **Arduino IDE**  
- **Blynk Library** (`BlynkSimpleEsp8266`)  
- **LiquidCrystal_I2C** for LCD display  
- **BlynkTimer** for scheduled updates  

---

## ⚡ Circuit Connections

- **Ultrasonic Sensor**
  - Trig → D7  
  - Echo → D8  
- **LEDs**
  - LED1 → D0  
  - LED2 → D3  
  - LED3 → D4  
  - LED4 → D5  
  - LED5 → D6  
- **Relay**
  - Relay → D3 (controls motor)  
- **LCD (I2C)**  
  - SDA → A4  
  - SCL → A5  

> Adjust GPIO pins in the code based on your ESP8266 board version.

---

## 📝 Features in Code

- `ultrasonic()` function reads tank water level using HC-SR04.  
- Displays **water level on LCD** and **LED indicators**.  
- Sends real-time water level to **Blynk virtual pin V0**.  
- Blynk button on **V1** controls motor relay (ON/OFF).  
- Configurable thresholds (`Level1` to `Level5`) for custom water level ranges.  
- Timer updates every 100ms for smooth readings.  

---

## 🚀 Installation & Setup

1. **Install Arduino IDE**: [https://www.arduino.cc/en/software](https://www.arduino.cc/en/software)  
2. **Install ESP8266 Board Manager**:  
   - File → Preferences → Additional Board Manager URLs → `http://arduino.esp8266.com/stable/package_esp8266com_index.json`  
3. **Install Libraries**:  
   ```text
   Blynk
   LiquidCrystal_I2C
