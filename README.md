# 🚴‍♂️ RideKit: ESPHome-Powered Smart Exercise Bike

**RideKit** is a DIY upgrade project that transforms a basic exercise bike into an interactive, servo-controlled smart trainer using ESPHome and an ESP32 board.

It provides real-time control over flywheel resistance, support for video sync via cadence sensing, and is designed to be modular, scalable, and home assistant–friendly.

---

## 📦 Features (Current & Planned)

### ✅ Current
- 🧠 Rotary encoder to adjust flywheel resistance in real time
- ⚙️ Servo-controlled magnetic resistance via PCA9685
- 📶 Wi-Fi OTA support for wireless updates
- 💡 Modular YAML structure for clarity and reusability
- 🛠️ Home Assistant integration-ready

### 🔜 Planned
- 🎥 Video playback sync based on pedal speed
- 📈 Cadence sensing
- 🧘‍♂️ Resistance “programs” or terrain simulation
- ❤️ BLE heart rate monitor integration
- 🎮 Home Assistant UI sliders & controls
- 🚵 Future expansion for display, buttons, and 3D ride generation

---

## 🔌 Hardware Summary

| Component                              | Purpose                         | GPIO(s)       |
|----------------------------------------|----------------------------------|---------------|
| ESP32-S3 DevKitC-1                     | Main controller board            | —             |
| PCA9685 (I²C PWM controller)           | Servo control for resistance     | SDA: GPIO21, SCL: GPIO16 |
| Hobby servo                            | Adjusts magnetic flywheel bar    | Channel 0 (PCA9685) |
| Rotary encoder                         | Manual resistance control        | A: GPIO18, B: GPIO19 |
| Cadence sensor (planned)               | Pedal speed detection            | TBD           |

---

## 📁 Project Structure

```plaintext
esphome/
├── ridekit.yaml                      # Main config entry point
├── secrets.yaml                      # Wi-Fi passwords (ignored by Git)
├── ridekit/
│   ├── control/
│   │   ├── pwm_controller.yaml
│   │   └── flywheel_resistance_servo.yaml
│   ├── inputs/
│   │   ├── buttons.yaml
│   │   └── flywheel_resistance_rotary_encoder.yaml
│   ├── sensors/
│   │   └── cadence.yaml
│   ├── display/
│   │   └── screen.yaml
