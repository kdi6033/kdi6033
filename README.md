<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=220&section=header&text=i2r%20AI%20IoT%20Platform&fontSize=50&animation=fadeIn&fontAlignY=38&desc=IoT%20·%20피지컬%20AI%20·%20온디바이스%20AI%20기반의%20스마트%20공장%20자동화%20솔루션&descAlignY=55&descAlign=50" />
</div>

<div align="center">
  <h3>Physical AI 기반 IoT 통합 플랫폼</h3>
  <div align="center">
    <a href="https://i2r.link">🌐 공식 홈페이지</a>
  </div>
</div>

---

## 🔷 i2r 의미?

**i2r (아이티알)** 은 **IoT PLC, 센서, 임베디드 시스템과 AI를 하나로 연결하는 통합 플랫폼**입니다.  
단순한 예제 코드가 아닌, **실제 현장 · 교육 · 제품화**를 모두 고려한 실전형 아키텍처를 제공합니다.

### 🚀 핵심 철학 (Core Values)
- **🔌 Industrial IoT**: 현장에서 즉시 사용 가능한 PLC와 센서 제어 기술.
- **🤖 Physical AI**: 클라우드 AI뿐만 아니라, 장비 스스로 판단하는 **On-Device AI** 구현.
- **🌐 Full-Stack Integration**: 하드웨어부터 웹(React), AI 서버(Python)까지 끊김 없는 연결.
- **🎓 Edu & Product**: 학생 교육부터 실제 제품 양산까지 가능한 확장성.

---


## 🗂️ i2r 플랫폼 아키텍처 (System Architecture)

i2r 플랫폼은 펌웨어, 서버, 문서, 그리고 배포 시스템이 유기적으로 연결된 **통합 생태계**입니다.

```text
                          ┌──────────────────────────┐
                          │       i2r Platform       │
                          │  github.com/kdi6033/     │
                          └─────────────┬────────────┘
                                        │
        ┌───────────────────────────────┼───────────────────────────────┐
        │                               │                               │
┌───────▼───────┐              ┌────────▼───────┐               ┌───────▼─────────┐
│  i2r 제품     │              │ Server / Cloud │               │  Documentation  │
│  (Board FW)   │              │ (React / API)  │               │  & Common Rules │
└───────┬───────┘              └────────┬───────┘               └─────────────────┘
        │                               │
 ┌──────┴──────┐      ┌─────────────────┴───────────────┐
 │ i2r-01      │      │ dashboard-react (React UI)      │
 │ i2r-02      │      │ api-node / python (Backend)     │
 │ i2r-03 (HMI)│      │ mqtt-bridge                     │
 │ i2r-04      │      └─────────────────────────────────┘
 │ i2r-05 (AI) │
 └──────┬──────┘
        │
┌───────▼──────────────────────────────────────────────────────────────┐
│                       Download / Distribution                        │
│                (Compiled Binaries .bin / OTA Updates)                │
│                     github.com/kdi6033/download                      │
└──────────────────────────────────────────────────────────────────────┘
```


```mermaid
graph TD
    %% Main Platform
    MAIN["i2r Platform<br/>(github.com/kdi6033)"] --> FW["i2r 제품<br/>(Board FW)"]
    MAIN --> CLOUD["Server / Cloud<br/>(React / API)"]
    MAIN --> DOCS["Documentation"]

    %% Firmware Branch
    FW --> I01[i2r-01<br/>i2r-02<br/>i2r-03<br/>i2r-04<br/>i2r-05]
    
    %% Cloud Branch
    CLOUD --> R1[dashboard-react]
    CLOUD --> A1[api-node / python]
    CLOUD --> M1[mqtt-bridge]

    %% Download Center (Linked from FW)
    FW -.-> DL["Download / Distribution<br/>(github.com/kdi6033/download)"]

    %% Styling
    style MAIN fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
    style FW fill:#FFF3E0,stroke:#FF9800,stroke-width:2px
    style DL fill:#E8F5E9,stroke:#4CAF50,stroke-width:2px
```


```mermaid
graph TD
    %% Main Platform
    MAIN["i2r Platform<br/>(github.com/kdi6033)"]:::root

    %% Define Subgraphs for Structure
    subgraph Hardware [Hardware & Firmware]
        direction TB
        FW["i2r 제품 (Board FW)"]:::hw
        FW --> I01[i2r-01]
        FW --> I02[i2r-02]
        FW --> I03["i2r-03 (HMI)"]
        FW --> I04[i2r-04]
        FW --> I05["i2r-05 (AI)"]
    end

    subgraph Service [Cloud Service]
        direction TB
        CLOUD["Server / Cloud<br/>(React / API)"]:::sw
        CLOUD --> R1[dashboard-react]
        CLOUD --> A1[api-node / python]
        CLOUD --> M1[mqtt-bridge]
    end

    subgraph Document [Guide]
        direction TB
        DOCS["Documentation<br/>& Rules"]:::doc
    end

    %% Connections
    MAIN --> FW
    MAIN --> CLOUD
    MAIN --> DOCS
    FW -.-> DL["Download / OTA Center<br/>(github.com/kdi6033/download)"]:::down

    %% Styles
    classDef root fill:#2196F3,stroke:#0D47A1,stroke-width:2px,color:white;
    classDef hw fill:#FFF3E0,stroke:#FF9800,color:black;
    classDef sw fill:#E8F5E9,stroke:#4CAF50,color:black;
    classDef doc fill:#F3E5F5,stroke:#9C27B0,color:black;
    classDef down fill:#ECEFF1,stroke:#607D8B,stroke-dasharray: 5 5;
    
    %% Flowchart Config (Optional: Add this to top if supported, else default curve)
    %% linkStyle default interpolate basis
```


### 📂 리포지토리 구성 상세

| **분류 (Category)** | **리포지토리 (Repositories)** | **설명 (Description)** |
| :--- | :--- | :--- |
| **펌웨어 FW** | `i2r-01` ~ `i2r-05` | 각 하드웨어 보드별 아두이노 펌웨어 소스 |
| **서버 Cloud** | `react`, `node-red` | 웹 대시보드 및 백엔드 API (Node.js/Python) |
| **배포 Center** | [`download`](https://github.com/kdi6033/download) | 컴파일된 바이너리(.bin) 및 OTA 업데이트 파일 |
| **교육 Edu** | `teach-iot`, `plc`, `sensor` | 학생 실습용 예제 및 아두이노 센서 라이브러리 |

---

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
