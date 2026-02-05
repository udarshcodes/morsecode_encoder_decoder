# Smart Morse Code Encoder–Decoder & Communication System 📡

**A Bidirectional IoT Transceiver bridging the gap between historical communication and modern digital logic.**

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Platform-Arduino_Uno-blue)
![Language](https://img.shields.io/badge/Language-C++_%7C_HTML/JS-orange)

## 📜 Project Overview
This project is an advanced **Morse Code Transceiver** capable of two-way communication. It acts as a bridge between a computer (Serial/Web Interface) and manual hardware inputs.

1.  **Encoder (English → Morse):** Type text on the computer/website, and the Arduino converts it into Morse code audio pulses (Buzzer) and visual feedback.
2.  **Decoder (Morse → English):** Use physical push-buttons to tap dots and dashes. The system uses a time-based algorithm to decode signals into English text in real-time.

---

## ✨ Key Features
* **Full-Duplex Communication:** Transmit and Receive simultaneously.
* **Smart "No-Resistor" Circuit:** utilizes internal `INPUT_PULLUP` resistors and PWM-based LCD contrast control to minimize hardware components.
* **Extended Dictionary:** Supports **Uppercase**, **Lowercase** (Custom Protocol), **Numbers**, and **Special Characters**.
* **Web Dashboard:** A custom-built HTML/JS interface using the **Web Serial API** to control the device directly from a Chrome/Edge browser.
* **Real-Time Decoding:** Decodes manual input instantly and sends completed words back to the computer.
* **Auto-Clear:** Smart display management automatically resets the screen after inactivity.

---

## 🛠️ Hardware Requirements
* **Microcontroller:** Arduino Uno R3
* **Display:** 16x2 LCD Module
* **Audio:** Piezo Buzzer
* **Inputs:** 2x Push Buttons (Tactile Switches)
* **Wiring:** Jumper Wires & Breadboard
* **Connection:** USB Cable (Type A to B)

### 🔌 Pin Configuration
| Component | Arduino Pin | Note |
| :--- | :--- | :--- |
| **LCD RS** | 12 | Register Select |
| **LCD E** | 11 | Enable |
| **LCD D4-D7** | 5, 4, 3, 2 | Data Lines |
| **Dot Button** | 6 | Input Pullup |
| **Dash Button** | 7 | Input Pullup |
| **Buzzer** | 8 | Positive Leg |

> **Note:** This circuit uses **Internal Pull-up Resistors**, so no external resistors are needed for the buttons.

---

## 🚀 Installation & Setup

### 1. Arduino Firmware
1.  Open the `Arduino_Code.ino` file in the Arduino IDE.
2.  Connect your Arduino Uno via USB.
3.  Select the correct **Board** and **Port** in Tools.
4.  Click **Upload**.
5.  *Important:* Close the Arduino Serial Monitor if you plan to use the Web Dashboard.

### 2. Web Dashboard
1.  Navigate to the `Web_Dashboard` folder.
2.  Open `index.html` in **Google Chrome** or **Microsoft Edge**.
3.  Click the **"Connect to Arduino"** button on the webpage.
4.  Select your Arduino COM port from the popup list.

---

## 📖 Usage Guide

### Mode A: Transmitting (Computer to Hardware)
1.  Open the Web Dashboard (or Serial Monitor).
2.  Type a sentence (e.g., "Hello World") and press **Enter**.
3.  The Arduino will beep the corresponding Morse sequence.
4.  The LCD will display the English letter on the top row and the Morse code on the bottom row.

### Mode B: Receiving (Hardware to Computer)
1.  Use the **Dot Button (Pin 6)** and **Dash Button (Pin 7)**.
2.  Tap a Morse sequence (e.g., `...` `---` `...`).
3.  The LCD displays the dots/dashes in real-time.
4.  Wait 1.2 seconds: The letter is decoded and added to the screen.
5.  Wait 2.5 seconds: The completed word is sent to the Web Dashboard/Serial Monitor.

---

## 🔮 Future Scope
* **Wireless Integration:** Adding HC-05 Bluetooth modules for wireless transmission.
* **Optical Comm (Li-Fi):** Replacing the buzzer with a Laser Diode for light-based data transfer.
* **Voice Synthesis:** Adding a Text-to-Speech module to read decoded words aloud for accessibility.

---

## 👨‍💻 Developer Info

**Designed & Developed by:** Udarsh Goyal

[<img src="https://img.shields.io/badge/GitHub-View_Profile-black?logo=github">](https://github.com/udarshcodes) 

> *This project was built for educational purposes to demonstrate embedded systems, serial communication, and algorithmic logic.*
