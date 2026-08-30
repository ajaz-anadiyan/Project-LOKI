# 🚀 Project Loki: Bidirectional Free-Space Optical Communication

**Project Loki** is a two-way laser communication system built for the NIMS Dubai Expo. It demonstrates NASA's latest Free-Space Optical (FSO) satellite technology by transmitting data wirelessly through beams of light instead of radio waves. 

The project features **two identical transceiver stations**. Both stations can send and receive audio data at the exact same time over a single optical link.

---

## 🌟 Key Features
* **Two-Way Link:** Simultaneous transmission and reception (Full-Duplex).
* **Signal Conditioning:** Comparators turn weak photodiode light signals into sharp digital square waves.
* **Logic-Level Control:** Low-power ESP32 pins safely switch a 5V laser using high-speed MOSFETs.
* **Dual Demo Inputs:** Supports live voice from a microphone or digital MP3 file streaming.

---

## 🛠️ How It Works

### Signal Flow Matrix
```text
               [ STATION 1 ]                                                                  [ STATION 2 ]
          Mic/MP3 ➔ ESP32 ➔ MOSFET ➔ Laser Diode =======(Laser Beam 1)=======> |Photodiode ➔ Comparator ➔ ESP32 ➔ Amp ➔ Speaker
                                                                       
Speaker 🡨 Amp 🡨 ESP32 🡨 Comparator 🡨 Photodiode <=======(Laser Beam 2)======= Laser Diode 🡨 MOSFET 🡨 ESP32 🡨 Mic/MP3
```


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

### 🖼️ Circuit Schematic & Wiring Guide
*(Paste your breadboard layout or circuit schematic below)*
![Transceiver Schematic](placeholders/transceiver_schematic.png)

---

## 🔬 Core Scientific Principles

* **Photoconductive Mode:** The BPW34 uses reverse-bias power to react fast enough to catch digital audio frequencies.
* **Threshold Adjustment:** A comparator filters out background room lights by looking only for the intense laser brightness.
* **Low-Side Switching:** The MOSFET bridges the 3.3V microcontroller logic and the 5V laser power supply safely on the ground line.

### 🖼️ Completed Prototype Models
*(Paste photos of your actual physical project boxes and models below)*
![Station 1 Prototype](placeholders/station1_model.jpg)
![Station 2 Prototype](placeholders/station2_model.jpg)
