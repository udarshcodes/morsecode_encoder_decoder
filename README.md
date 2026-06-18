# Smart Morse Code Encoder-Decoder & Communication System

A bidirectional IoT transceiver bridging the gap between historical communication and modern digital logic.

## Live Demo
No live demo is currently available. The project requires a local Arduino connection via USB to function.

## About
This is an educational personal project built to explore embedded systems, serial communication, and time-based algorithmic logic. It serves as a two-way Morse code communication system that connects a web interface to a physical Arduino setup. Users can send English text from the browser to be emitted as Morse code, or tap Morse code on physical buttons to be decoded on screen. The scope is strictly a local hardware-software integration. Note that the Arduino source code is currently not present in the repository and must be supplied by the user.

## Features
* Send text messages from the browser to the Arduino, which outputs them as Morse code audio (buzzer) and visual signals.
* Tap physical buttons (dot and dash) on the hardware to send Morse code back to the browser.
* View real-time decoding of the Morse code into English text on the web interface.
* Connect directly to the hardware via the browser without requiring a backend server.

## Tech Stack

| Layer | Technology |
| :--- | :--- |
| Frontend | HTML, CSS, JavaScript (Vanilla) |
| Browser API | Web Serial API |
| Hardware | Arduino Uno R3, 16x2 LCD, Piezo Buzzer, Tactile Buttons |

## Architecture
The system consists of a static HTML frontend and an Arduino microcontroller connected via USB. The browser uses the Web Serial API to establish a direct serial connection to the Arduino. When a user types a message, the JavaScript frontend sends the string over serial to the Arduino, which translates it into buzzer beeps and LCD text. Conversely, when a user taps the physical push buttons, the Arduino measures the timing of the presses to decode the Morse characters and sends the decoded English characters back over the serial connection to be displayed on the web page.

## Running Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/udarshcodes/morsecode_encoder_decoder.git
   cd morsecode_encoder_decoder
   ```
2. Set up the hardware:
   Wire the Arduino Uno according to the `circuit.png` diagram.
3. Upload firmware:
   Open your Arduino IDE, write or obtain the corresponding Morse code firmware, and upload it to the board. Close the Arduino IDE Serial Monitor once uploaded.
4. Launch the web interface:
   Open `index.html` directly in Google Chrome or Microsoft Edge.
5. Connect:
   Click "Connect to Arduino" on the web page and select your Arduino's COM port.

## Project Structure

```text
.
├── LICENSE
├── README.md
├── circuit.png
└── index.html
```

## What I Learned
* **Direct Browser-Hardware Communication:** Utilizing the Web Serial API eliminates the need for an intermediate Node.js or Python backend, reducing latency and architectural complexity.
* **Hardware Debouncing and Timing:** Handling button press durations and intervals on the Arduino is necessary for accurate Morse code decoding, rather than relying on the less predictable event loop of the browser.
* **Browser Compatibility Tradeoffs:** Relying on the Web Serial API means the interface is currently restricted to Chromium-based browsers (Chrome, Edge), sacrificing broad cross-browser support for simplicity in architecture.
* **Minimal Component Design:** Using the Arduino's internal pull-up resistors reduced the need for external resistors on the breadboard, leading to a cleaner hardware layout.

