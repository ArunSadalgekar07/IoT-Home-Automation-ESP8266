# 🏡 IoT Home Automation with ESP8266 (Arduino IoT Cloud + DHT + Servo + Relay)

This project is a Wi-Fi-based home automation system using the **ESP8266 NodeMCU**, which integrates with **Arduino IoT Cloud** to control lights, a fan (via relays), and a gate (via servo motor). It also monitors **temperature** and **humidity** using a **DHT11 sensor**.

## 📦 Features

- 🌡️ Real-time Temperature & Humidity Monitoring (DHT11)
- 💡 Remote Light Control via Relay
- 🌀 Fan Control via Relay
- 🚪 Servo-Controlled Gate Operation
- ☁️ Arduino IoT Cloud Integration for Remote Control & Monitoring
- 📶 Wi-Fi Reconnection Handling

## 🧰 Hardware Used

| Component        | Description                      |
|------------------|----------------------------------|
| ESP8266 NodeMCU  | Wi-Fi microcontroller board      |
| DHT11 Sensor     | Temperature & humidity sensor    |
| Relay Module     | For controlling light and fan    |
| Servo Motor      | For gate control                 |
| Jumper Wires     | For connections                  |

## 🛠️ Software Used

- Arduino IDE
- Arduino IoT Cloud
- ESP8266WiFi Library
- DHT Library
- Servo Library

## 📐 Pin Configuration

| Function         | ESP8266 Pin |
|------------------|-------------|
| Light Relay      | D1          |
| Fan Relay        | D2          |
| Servo Motor      | D5          |
| DHT11 Data Pin   | D8 (GPIO15) |

## 🚀 How It Works

1. **Wi-Fi Connection:** Connects to predefined Wi-Fi using `ESP8266WiFiMulti`.
2. **Arduino IoT Cloud:** Syncs with the Arduino IoT Cloud using `thingProperties.h`.
3. **Sensor Readings:** Periodically reads temperature and humidity using the DHT11 sensor.
4. **Cloud Variables:**
   - `temperature` & `humidity` are updated in the cloud.
   - `light` & `fan` are boolean controls to toggle relays.
   - `gateControl` is used to open/close the gate via servo.
5. **Fail Handling:** Reconnects to Wi-Fi if the connection drops.

## 📲 Cloud Variables

| Variable      | Type    | Purpose                            |
|---------------|---------|------------------------------------|
| `light`       | Boolean | Turns light ON/OFF                 |
| `fan`         | Boolean | Turns fan ON/OFF                   |
| `gateControl` | Boolean | Opens/closes the gate              |
| `temperature` | Float   | Stores latest temperature reading  |
| `humidity`    | Float   | Stores latest humidity reading     |


### System Flow Summary:
1. Wi-Fi connection established ✅  
2. Environmental sensors read 🌡️💧  
3. Gate control sequence executed (open → close)  

## 📎 Notes

- Wi-Fi credentials are hardcoded (ssid, password).
- Make sure `thingProperties.h` is configured properly from Arduino IoT Cloud.
- Adjust servo angles as per your hardware setup.

## 📸 Preview
![image](https://github.com/user-attachments/assets/5532ee3d-704a-465e-b29e-3bd8deab24b7)

