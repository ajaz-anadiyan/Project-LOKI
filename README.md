# 🚀 Project Loki: Bidirectional Free-Space Optical Communication

**Project Loki** is a two-way laser communication system built for the NIMS Dubai Expo. It demonstrates NASA's latest Free-Space Optical (FSO) satellite technology by transmitting data wirelessly through beams of light instead of radio waves. 

The project features **two identical transceiver stations**. Both stations can send and receive audio data at the exact same time over a single optical link.

---

## 🌟 Key Features
* **Two-Way Link:** Simultaneous transmission and reception (Full-Duplex).
* **Signal Conditioning:** Comparators turn weak photodiode light signals into sharp digital square waves.
* **Logic-Level Control:** Low-power ESP32 pins safely switch a 5V laser using high-speed MOSFETs.
* **Dual Demo Inputs:** Supports live voice from a microphone or digital MP3 file streaming.
![Side view](<./Demonstration/Side view.png>)
---

## 🛠️ How It Works

### Signal Flow Matrix
![Project Loki Transceiver Diagram](https://kroki.io/plantuml/svg/eNqtVm1v2kgQ_u5fMSJSk0ixitemgRO1uhi7RWcDwk4bqeqHBRawYrxovVwvd8p_v_VL8BaTNNdmI0Vo5tmZ2efZGe-HTBAu9ttEOwdd18FJKEkh4iTNdoTTVMCUsxXNspilJIGQiv0uB2rZXZxKBNnCnCzu1pzt0-WCJYyDqDcrqAXb7lgqbaG4TyhwuhAkXSdUgQzpiuwT4bFUjMmWQiuka0bhZtS6AsxjklxBJkPrGeXx6vQ-p6jgzHBRzxychoTxPxQMU3HO8todxlPKoavYww1Zsu9xuoYVSTKqVRRJM9_Bp3i90R0Zj5NMkkQSKgQ9YmYnmSFrCv9qINfgwFNVpdf1sOeUPsaXlFf2noXNQbewK2dqe8Y1wgdrSeOcJUvtQVNyrqRFnuOplMVqpnQGw45rHKc0TcvodH6Mf9CxSnFeXpZtLI_PJQ9iAxflJRoke3r5RBltr3eqjDbqWs514-Tmux4ui6tSzuiCxn8d5fvIKU2fTjj0rGZC4x02LXyc0Oh02-YwP_c5vP_FJbeGEY5GkzG0jd-J83iJWnW4FvT7oSBC9qRtVzoU_yrxW6okoew0CYSL6PayVYHz9XU0DqaWZcAIhRDEi29AMgiM2u-GU91EEDg3hcs1ZNbo1rZrxFiP7ncUgknouVG5f9JEdT5LvZbgE9m3MIzZkhZQv4E8_AgM0LnsL6Hb4NYVuYpZJqrhE8Xhl_aHJimHS3NgZHbEyGD6xbRgumGCLQ91TvM6Zz-cyA_MngmO7ATZEoLxAuc0cTWDUFI4a2ICfNvrmp1rXOgwxE6BxE1gV59s5EzaUXJHy4yh0aRuqlDh1H5HZXSmUDpTHLi2Y8UcPjL6av2AXrcf0E_74aT08ALt0Qu1R89p_yg--rn4JRSj59UvUSE6IT9S5K_9DlLlR4r8igPXdqyYqzQPL58y8NyYKWsP0GmmKqrQ86OmijFBL5g1JdZHTw8blRuFGqQOG6QMG8Xho1dqjck0GjnYBx-H7gz80fjPEC6-xPLjdpPmFzeTby_5fbuHiP4t4A18jrN4Lr__mHP2Pbv8neRyDutfz1zPkusqf098k48YeTZ5lf6A_kp-FaF4170_uzbkH7b7c7vkd0Dle8DZkDSlCRj9t3O7_zbH21o-M_Mox4FzHf5PUKQG1T7QdLnfav8BYnfZFA==)

---

## 🎧 Expo Demonstration Modes

Visitors can interact with the project using two different modes:

### 1. Live Voice Mode (Intercom Demo)
* Speaks into the microphone at Station 1.
* The ESP32 digitizes the voice and flashes it across the room via the laser.
* Station 2 receives the beam and plays the audio instantly through the speaker.

### 2. MP3 Music Mode (Data Streaming Demo)
* Plays a mp3 audio file from laptop/mobile to other station speaker.
* Demonstrates that optical links can handle high-bandwidth digital data streams.

### 🖼️ Expo Setup Layout
![Top view](<./Demonstration/Top view.png>)

---

## 📋 Component Checklist (Per Station)

Both stations use identical hardware:
* **Brain:** 1x ESP32 Microcontroller
* **Light Source:** 1x 5V Laser Diode
* **Laser Driver:** 1x N-Channel Logic-Level MOSFET (IRLZ44N)
* **Receiver:** 1x BPW34 PIN Photodiode
* **Signal Cleaner:** 1x Voltage Comparator (LM393)
* **Audio Input:** 1x Microphone Module
* **Audio Output:** 1x Audio Amplifier Module & 8Ω Speaker

---

## 🔬 Core Scientific Principles

* **Photoconductive Mode:** The BPW34 uses reverse-bias power to react fast enough to catch digital audio frequencies.
* **Threshold Adjustment:** A comparator filters out background room lights by looking only for the intense laser brightness.
* **Low-Side Switching:** The MOSFET bridges the 3.3V microcontroller logic and the 5V laser power supply safely on the ground line.
