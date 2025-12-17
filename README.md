[README.md](https://github.com/user-attachments/files/24215948/README.md)

# ESP8266 Bird Detection & Telegram Alert System

## Project Overview
This project implements a **bird detection and alert system** using an **ESP8266 (NodeMCU)**. It detects birds by monitoring a **laser beam and light receiver setup**. When the beam is interrupted, the system triggers a **local alarm (LED and buzzer)** and sends a **Telegram alert** to a predefined chat.

The system is suitable for **farms, gardens, or restricted areas** where bird intrusion needs to be detected and reported remotely.

---

## Features
- Real-time bird detection using a laser and light receiver
- Local alerts using an LED and buzzer
- Remote alerts via **Telegram Bot**
- Secure HTTPS communication using SSL certificates
- Wi-Fi enabled monitoring

---

## Hardware Requirements
- ESP8266 (NodeMCU)
- Laser module
- Light receiver (LDR / photodiode / laser receiver module)
- LED
- Buzzer
- Connecting wires
- Stable Wi-Fi connection

---

## Pin Configuration

| Component        | ESP8266 Pin |
|------------------|-------------|
| LED              | D4          |
| Buzzer           | D3          |
| Light Receiver   | D8          |
| Laser Module     | D7          |

---

## Software & Libraries
Ensure the following libraries are installed in the Arduino IDE:

- ESP8266WiFi
- WiFiClientSecure
- UniversalTelegramBot
- ArduinoJson

---

## Configuration
Update the following variables in the code with your own credentials:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";

#define BOTtoken "YOUR_TELEGRAM_BOT_TOKEN"
#define CHAT_ID "YOUR_TELEGRAM_CHAT_ID"
```

---

## How It Works
1. The ESP8266 connects to Wi-Fi.
2. The laser remains ON continuously.
3. The light receiver monitors the laser beam.
4. When a bird interrupts the beam:
   - LED turns ON
   - Buzzer turns ON
   - Telegram alert is sent
5. When the beam is restored:
   - LED turns OFF
   - Buzzer turns OFF

---

## Sample Telegram Alert
```
Warning: Birds In the farm!
```

---

## Notes
- The function name `sendSMSAlert()` sends **Telegram messages**, not SMS.
- Without delay logic, repeated alerts may be sent if the beam remains broken.
- Consider adding a cooldown timer for production use.

---

## Applications
- Farm bird control
- Perimeter security
- Smart agriculture projects
- IoT learning and demonstrations 

---

## License
This project is for **educational and academic use**.
