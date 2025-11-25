# Ultimate-Biometric-Door-Lock
ULTIMATE BIOMETRIC DOOR LOCK – Built by Andre (South Africa) 🇿🇦 

The most secure &amp; polished Arduino fingerprint lock in 2025.  

If this saved you weeks of work or you’re using it commercially: →### Buy me a braai, a beer, or keep the lights on! 🇿🇦
[![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/Elzanne6553)

- [R100 – Coffee & rusks](https://paypal.me/Elzanne6553/100ZAR)  
- [R250 – Braai pack](https://paypal.me/Elzanne6553/250ZAR)  
- [R500 – Weekend vibes](https://paypal.me/Elzanne6553/500ZAR)  
- [R1000 – Legend status](https://paypal.me/Elzanne6553/1000ZAR)  
- [Custom amount – you’re the boss](https://paypal.me/Elzanne6553)

# Biometric Security System v2.1
A professional-grade biometric door lock system built with Arduino, featuring fingerprint authentication, menu-based controls, and enterprise-level security protocols.

## 🌟 Features

### Core Functionality
- **Fingerprint Authentication** - Supports up to 162 users with on-sensor storage
- **Menu-Based Interface** - Intuitive LCD navigation with button control
- **Smart User Management** - Add, delete, and manage users with ease
- **Multi-Layer Security** - Admin verification for all critical operations

### Security Features
- ✅ **Admin-Only Access** - IDs 1-6 have administrative privileges
- ✅ **Duplicate Prevention** - Ensures each fingerprint is unique
- ✅ **Factory Reset Protection** - Three-layer authentication required
- ✅ **Auto-Timeout** - 20-second inactivity timeout on all menus
- ✅ **Unknown User Alerts** - Visual and audio feedback for unauthorized attempts
- ✅ **First-Time Setup Mode** - Automatic recovery if all users deleted

### User Experience
- **Batch Enrollment** - Add multiple users in one session
- **Smart Delete Navigation** - Only shows existing users with position tracking (e.g., "ID #003 (2/10)")
- **Fast Scroll** - Hold button >3s to auto-scroll through users every 2.5s
- **Enrollment Retry** - Up to 3 attempts for fingerprint matching
- **LCD Feedback** - Clear on-screen instructions for all operations
- **RGB Status LED** - Color-coded system states
- **Audio Feedback** - Success/failure beeps and tones

## 🔧 Hardware Requirements

### Components
| Component | Specification | Quantity |
|-----------|--------------|----------|
| Arduino Uno | ATmega328P | 1 |
| Fingerprint Sensor | Adafruit R307 or compatible | 1 |
| I2C LCD Display | 16x2 (0x27 or 0x3F address) | 1 |
| RGB LED | Common Cathode | 1 |
| Active Buzzer | 5V | 1 |
| Relay Module | 5V, 10A | 1 |
| Push Button | Momentary | 1 |
| Resistors | 220Ω | 3 |

### Wiring Diagram

```
Arduino Uno Connections:
├─ Fingerprint Sensor (R307)
│  ├─ VCC    → 5V
│  ├─ GND    → GND
│  ├─ TX     → Pin 2 (RX)
│  └─ RX     → Pin 3 (TX)
│
├─ I2C LCD (16x2)
│  ├─ VCC    → 5V
│  ├─ GND    → GND
│  ├─ SDA    → A4
│  └─ SCL    → A5
│
├─ RGB LED (Common Cathode)
│  ├─ R      → Pin 6 (via 220Ω)
│  ├─ G      → Pin 9 (via 220Ω)
│  ├─ B      → Pin 10 (via 220Ω)
│  └─ GND    → GND
│
├─ Buzzer
│  ├─ +      → Pin 5
│  └─ -      → GND
│
├─ Push Button
│  ├─ Pin 1  → Pin 8
│  └─ Pin 2  → GND
│
└─ Relay Module
   ├─ VCC    → 5V
   ├─ GND    → GND
   └─ IN     → Pin 12
```

## 📦 Installation

### 1. Install Required Libraries

```cpp
// Via Arduino Library Manager:
- Adafruit Fingerprint Sensor Library (v2.1.3+)
- LiquidCrystal I2C (v2.0.0+)
```

### 2. Upload Code

1. Clone this repository
   ```bash
   git clone https://github.com/Andre6553/biometric-security-system.git
   ```

2. Open `biometric_security_system_v2_1_final.ino` in Arduino IDE

3. Select **Tools → Board → Arduino Uno**

4. Select your COM port

5. Click **Upload**

### 3. First-Time Setup

On first boot with an empty sensor:
1. System displays **"FIRST TIME SETUP"**
2. Follow on-screen prompts to enroll **Admin #1**
3. System retries until successful
4. Shows **"SETUP COMPLETE!"** when done

## 🎮 Usage Guide

### Entering the Menu

1. **Hold button** for 2 seconds
2. Scan **Admin fingerprint** (ID 1-6)
3. Access **MAIN MENU**

### Menu Options

#### 📝 Enroll New User
1. System finds next available ID
2. Scan finger **twice** for confirmation
3. On mismatch: Up to **3 attempts** allowed
4. After success: Choose "**Add Another?**" to continue or exit

#### 🗑️ Delete User
1. Display shows: **"ID #003 (2/10)"** (current/total)
2. **Single click**: Jump to next user
3. **Hold >3s**: Auto-scroll every 2.5s
4. **Hold 2s**: Confirm selection
5. Choose **YES/NO** to confirm deletion

#### 🔄 Factory Reset
1. **Hold button** for 10 seconds (from ANY mode)
2. Scan **Admin fingerprint**
3. Confirm with **YES/NO** dialog
4. All data wiped and system reboots

### Button Controls

| Action | Function |
|--------|----------|
| **Single Click** | Navigate menu / Increment ID |
| **Hold 2 seconds** | Enter menu / Confirm selection |
| **Hold 3+ seconds** | Fast scroll (in delete mode) |
| **Hold 10 seconds** | Initiate factory reset |

## 🔒 Security Architecture

### Authentication Layers

1. **Physical Access** - Button must be accessible
2. **Biometric Verification** - Admin fingerprint required
3. **Explicit Confirmation** - YES/NO dialogs for critical actions

### Admin Privileges (IDs 1-6)

- ✅ Access menu system
- ✅ Enroll new users
- ✅ Delete existing users
- ✅ Perform factory reset

### Regular Users (IDs 7-162)

- ✅ Unlock door/relay
- ❌ No administrative access

### Auto-Recovery Features

- **20-second timeout** on all menus
- **Automatic setup mode** if 0 users detected
- **Periodic user count check** every 5 seconds

## ⚙️ Technical Specifications

### System Modes

```cpp
MODE_NORMAL          // Idle, waiting for fingerprint
MODE_MENU            // Main menu navigation
MODE_ADMIN_VERIFY    // Admin authentication
MODE_ENROLL          // Enrolling new fingerprint
MODE_DELETE_SELECT   // Selecting user to delete
MODE_FACTORY_RESET   // Factory reset confirmation
```

### Timing Constants

```cpp
DEBOUNCE_MS      = 50     // Button debounce
HOLD_TIME_MS     = 2000   // Menu/confirm hold time
RESET_HOLD_MS    = 10000  // Factory reset hold time
RELAY_TIME       = 5000   // Door unlock duration
SCROLL_INTERVAL  = 2500   // Auto-scroll speed
MENU_TIMEOUT     = 20000  // Inactivity timeout
```

### Memory Usage

- **Flash**: ~15KB / 32KB (47%)
- **RAM**: ~1.2KB / 2KB (60%)
- **EEPROM**: Not used (all data on sensor)

## 🐛 Troubleshooting

### LCD Shows Nothing
- Check I2C address (try 0x3F if 0x27 fails)
- Verify SDA/SCL connections
- Adjust contrast potentiometer

### Fingerprint Not Recognized
- Clean sensor surface
- Ensure finger is dry
- Re-enroll if persistent
- Check sensor wiring

### System Locked (No Users)
- Wait 5 seconds for auto-recovery
- System enters First-Time Setup
- Enroll new Admin #1

### Compile Errors
- Update Adafruit Fingerprint library
- Update LiquidCrystal_I2C library
- Check board selection (Arduino Uno)

## 📊 Performance

- **Authentication Speed**: <2 seconds
- **Enrollment Time**: ~15 seconds per user
- **False Accept Rate**: <0.001%
- **False Reject Rate**: <1%
- **Operating Temperature**: 0-50°C
- **Fingerprint Capacity**: 162 users

## 🛣️ Roadmap

- [ ] EEPROM logging for access history
- [ ] Wi-Fi/Bluetooth connectivity
- [ ] Mobile app integration
- [ ] Multiple relay control
- [ ] Real-time clock integration
- [ ] Battery backup support

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Your Name**
- GitHub: [@Andre6553](https://github.com/Andre6553)

## 🙏 Acknowledgments

- Adafruit for the fingerprint sensor library
- Arduino community for support and resources
- All contributors who helped improve this project

## 📞 Support

For issues, questions, or suggestions:
- Open an [Issue](https://github.com/yourusername/biometric-security-system/issues)
- Start a [Discussion](https://github.com/yourusername/biometric-security-system/discussions)

---

⭐ **If this project helped you, please give it a star!** ⭐
