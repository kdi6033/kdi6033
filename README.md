# 김동일 | i2r – IoT PLC & Sensor Platform

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=220&section=header&text=i2r%20AI%20IoT%20Platform&fontSize=50&animation=fadeIn&fontAlignY=38&desc=Connecting%20Physical%20World%20to%20AI%20Cloud&descAlignY=55&descAlign=50" />
</div>

<div align="center">
  <h3>Physical AI 기반 IoT 통합 플랫폼</h3>
  <a href="https://i2r.link">🌐 Official Website</a> | 
  <a href="mailto:kdi6033@gmail.com">📧 Contact Me</a>
</div>

---

## 🔷 What is i2r?

**i2r (아이티알)** 은 **IoT PLC, 센서, 임베디드 시스템과 AI를 하나로 연결하는 통합 플랫폼**입니다.  
단순한 예제 코드가 아닌, **실제 현장 · 교육 · 제품화**를 모두 고려한 실전형 아키텍처를 제공합니다.

### 🚀 핵심 철학 (Core Values)
- **🔌 Industrial IoT**: 현장에서 즉시 사용 가능한 PLC와 센서 제어 기술.
- **🤖 Physical AI**: 클라우드 AI뿐만 아니라, 장비 스스로 판단하는 **On-Device AI** 구현.
- **🌐 Full-Stack Integration**: 하드웨어부터 웹(React), AI 서버(Python)까지 끊김 없는 연결.
- **🎓 Edu & Product**: 학생 교육부터 실제 제품 양산까지 가능한 확장성.

---

## 🗂️ i2r Platform Structure

i2r 플랫폼은 기능별로 특화된 **독립 리포지토리(Series)** 로 구성되어 있습니다.

| Series | Description (Repository) | Key Features |
| :--- | :--- | :--- |
| **[`i2r`](https://github.com/kdi6033/i2r)** | 🔰 **메인 플랫폼** | 전체 아키텍처, 통합 문서, 시작 가이드 |
| **[`i2r-01`](https://github.com/kdi6033/i2r-01)** | ⚡ **Basic PLC** | 디지털 입출력(Digital I/O), 릴레이 제어 |
| **[`i2r-02`](https://github.com/kdi6033/i2r-02)** | ⏱️ **Automation** | 타임 스케줄러, 자동 제어 로직, 타이머 |
| **[`i2r-03`](https://github.com/kdi6033/i2r-03)** | 🖥️ **HMI System** | 임베디드 UI, LCD 터치 스크린, 작화 솔루션 |
| **[`i2r-04`](https://github.com/kdi6033/i2r-04)** | ⚙️ **Actuator** | 모터(Step/Servo) 제어, 정밀 동작 구현 |
| **[`i2r-05`](https://github.com/kdi6033/i2r-05)** | 🧠 **AI & Robot** | **ESP32-S3 기반**, On-Device AI, 로봇 제어 |

---

## 🤖 **i2r AI Auto-Programmer (For Users)**
**📢 i2r 제품 사용자 필독!**  
이 플랫폼을 사용하는 가장 강력한 방법은 **AI와 협업**하는 것입니다.  
아래 **[System Prompt]**를 복사해서 **ChatGPT / Claude**에게 입력하세요.  
kdi6033이 설계한 아키텍처를 AI가 완벽하게 이해하고 코드를 짜줍니다.

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
2. **Frontend Code**: Provide the React component (`.tsx`) to monitor/control it.
3. **Explanation**: Briefly explain how the data flows via MQTT.
```

---

## 📊 **GitHub Activity**

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=kdi6033&show_icons=true&theme=radical&count_private=true" height="150" alt="kdi6033's GitHub Stats" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=kdi6033&layout=compact&theme=radical" height="150" alt="Top Languages" />
</div>
