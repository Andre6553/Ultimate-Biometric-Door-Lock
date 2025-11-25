# Ultimate-Biometric-Door-Lock
ULTIMATE BIOMETRIC DOOR LOCK – Built by Andre (South Africa) 🇿🇦 The most secure &amp; polished Arduino fingerprint lock in 2025.  If this saved you weeks of work or you’re using it commercially: →### Buy me a braai, a beer, or keep the lights on! 🇿🇦
[![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/Elzanne6553)

- [R100 – Coffee & rusks](https://paypal.me/Elzanne6553/100ZAR)  
- [R250 – Braai pack](https://paypal.me/Elzanne6553/250ZAR)  
- [R500 – Weekend vibes](https://paypal.me/Elzanne6553/500ZAR)  
- [R1000 – Legend status](https://paypal.me/Elzanne6553/1000ZAR)  
- [Custom amount – you’re the boss](https://paypal.me/Elzanne6553)

Zapper / SnapScan QR codes coming soon (watch this space 😉)

# Ultimate Biometric Door Lock v2.2  
**The most secure & polished Arduino fingerprint lock in the world – 2025**

[![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white)](https://www.arduino.cc/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
[![Made in South Africa](https://img.shields.io/badge/Made%20in-South%20Africa-%23127B55?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cmVjdCB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIGZpbGw9IiMxMjdCNDUiLz48cGF0aCBkPSJNMTIgMkwyMSAxMEgyMSAxNEgzIDE0SDMgMTBIMTJaIiBmaWxsPSJ3aGl0ZSIvPjxwYXRoIGQ9Ik0zIDE0SDIxVjIySDEyTDEyIDE0SDNaIiBmaWxsPSJ5ZWxsb3ciLz48cGF0aCBkPSJNMyAxMEgyMVYxMkgxMkwxMiAySDNaIiBmaWxsPSJibGFjayIvPjwvc3ZnPg==)](https://en.wikipedia.org/wiki/South_Africa)

Built from the ground up by **Andre** – South Africa 🇿🇦  
This is the **ultimate** Arduino biometric door lock in 2025.  
Zero bugs. Military-grade security. Beautiful UX.

## Features (Everything You Dreamed Of)

### Core
- 162-user capacity (on-sensor storage)
- Full menu system with single button
- RGB LED + buzzer feedback
- 16×2 I2C LCD with crystal-clear messages

### Security (Unbreakable)
- Admin-only access (IDs 1–6)
- 100 % duplicate-proof enrollment
- Factory reset = **10-second hold → Admin finger → YES/NO confirm**
- Auto-recovery if all users deleted (never bricked)
- 20-second timeout everywhere
- Fast-scroll + position counter in delete mode

### User Experience
- Batch enrollment (“Add another?”)
- Smart delete: only shows existing users → “ID #042 (7/53)”
- Hold >3s → auto-scroll every 2.5s
- First-time setup with retry loop
- Color-coded RGB states

## Hardware (Cheap & Easy)

| Component               | Qty |
|-------------------------|-----|
| Arduino Uno             | 1   |
| R307 / AS608 Fingerprint| 1   |
| 16×2 I2C LCD (0x27/0x3F)| 1   |
| Common-cathode RGB LED  | 1   |
| Active buzzer           | 1   |
| 5V relay module         | 1   |
| Push button             | 1   |
| 220 Ω resistors         | 3   |

Full wiring diagram in [WIKI → Wiring](https://github.com/Andre6553/Ultimate-Biometric-Door-Lock/wiki/Wiring)

## Quick Start

1. Install libraries (Arduino IDE → Library Manager)
   - Adafruit Fingerprint Sensor Library
   - LiquidCrystal I2C

2. Clone & upload
```bash
git clone https://github.com/Andre6553/Ultimate-Biometric-Door-Lock.git
