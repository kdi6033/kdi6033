## Hi there 👋

# 👋 Hello, World! I'm kdi6033 (Dongil Kim)

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=220&section=header&text=i2r%20AI%20IoT%20Platform&fontSize=50&animation=fadeIn&fontAlignY=38&desc=Connecting%20Industrial%20PLC%20to%20AI%20Cloud&descAlignY=55&descAlign=50" />
</div>

### 🚀 **Professor & AIoT Architect**
> **"Making Industrial IoT Intelligent & Accessible"**  
> We bridge the gap between **ESP32 PLCs** and **Generative AI**. Our mission is to let anyone control industrial hardware using natural language.

---

## 🛠️ **The "i2r" Ecosystem**

My work spans from **Embedded Firmware** to **Cloud AI**, creating a seamless pipeline for industrial automation.

| Layer | Technology Stack | Key Repositories |
| :--- | :--- | :--- |
| **🧠 AI & Data** | **Python**, **ChatGPT API**, TensorFlow Lite | `backend_python` (AI Server) |
| **☁️ Cloud/Web** | **React**, **Node-RED**, **MQTT**, MongoDB | [`react`](https://github.com/kdi6033/react), [`node-red`](https://github.com/kdi6033/node-red) |
| **📟 Firmware** | **Arduino (C++)**, PlatformIO, FreeRTOS | [`i2r-04`](https://github.com/kdi6033/i2r-04), [`i2r-05`](https://github.com/kdi6033/i2r-05) (ESP32-S3) |
| **⚙️ Hardware** | **ESP32 PLC**, RS485, Modbus, LVGL UI | [`i2r`](https://github.com/kdi6033/i2r), [`plc`](https://github.com/kdi6033/plc) |

---

## 🤖 **i2r AI Auto-Programmer (For Users)**
**📢 i2r 제품 사용자 필독!**  
더 이상 코드를 직접 짜지 마세요. 아래 **[System Prompt]**를 복사해서 **ChatGPT / Claude / Gemini**에게 붙여넣으세요.  
그리고 **"온도가 40도 넘으면 1번 릴레이 켜줘"**라고 말만 하세요. AI가 펌웨어와 웹 코드를 다 짜줍니다.

### 👉 **Copy This Prompt to Your AI:**

```markdown
# Role: i2r IoT Solutions Architect
You are an expert developer characterizing the "i2r" IoT PLC ecosystem created by kdi6033.

# Technical Context
1. **Hardware**: i2r-04 / i2r-05 (ESP32-based Industrial PLC).
2. **Communication**: MQTT over WiFi. JSON format is mandatory.
   - Topic: `i2r/{user_email}/in` (Cloud -> Device)
   - Topic: `i2r/{user_email}/out` (Device -> Cloud)
3. **Software Stack**:
   - Firmware: Arduino framework (C++). Use `ArduinoJson` and non-blocking `millis()`.
   - Frontend: React (TypeScript) or Node-RED.

# Task
When the user asks for a feature (e.g., "Control motor based on temperature"):
1. **Firmware Code**: Provide the complete `.ino` file for ESP32.
2. **Frontend Code**: Provide the React component ([.tsx](cci:7://file:///d:/homepage/react/frontend/src/App.tsx:0:0-0:0)) to monitor/control it.
3. **Explanation**: Briefly explain how the data flows via MQTT.

# Json Protocol Example
- Command: `{"command": "bindIO", "mac": "...", "portNo": 1, "value": true}`
- Status: `{"mac": "...", "temp": 36.5, "in": [0,0,0,0], "out": [1,0,0,0]}`

