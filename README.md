📡 IoT-Based Bidirectional People Counter with Automatic Light Control

 📌 Overview

This project implements a **bidirectional people counting system using ultrasonic sensors and Arduino**. It detects the direction of movement and updates the count accordingly.

The system also includes **automatic light control using a relay**, making it a complete smart automation solution.

* ➕ Increases count when a person enters
* ➖ Decreases count when a person exits
* 💡 Turns ON light when people are present
* 🌑 Turns OFF light when no one is inside

---

🚀 Features

* 🔄 Bidirectional Entry/Exit Detection
* 👨‍👩‍👧 Real-Time People Counting
* 💡 Automatic Light Control
* 📟 LCD Display Output (16x2)
* ⚡ Low Cost and Efficient System

---

 🛠️ Hardware Used

* Arduino Uno (or compatible board)
* 2 × Ultrasonic Sensors (HC-SR04)
* 16x2 LCD Display
* Relay Module
* Jumper Wires
* Power Supply

---

 🔌 Pin Configuration

| Component                   | Arduino Pin      |
| --------------------------- | ---------------- |
| LCD RS, EN, D4–D7           | 2, 3, 4, 5, 6, 7 |
| Ultrasonic Sensor 1 Trigger | A1               |
| Ultrasonic Sensor 1 Echo    | A0               |
| Ultrasonic Sensor 2 Trigger | A3               |
| Ultrasonic Sensor 2 Echo    | A2               |
| Relay Module                | 8                |

---

⚙️ Working Principle

Two ultrasonic sensors are placed at an entry/exit point to detect direction:

 ➤ Entry (Count +1)

* Sensor 1 detects first
* Sensor 2 detects next
* Person count increases

 ➤ Exit (Count -1)

* Sensor 2 detects first
* Sensor 1 detects next
* Person count decreases

 ➤ Light Automation Logic

* If count > 0 → Light ON
* If count = 0 → Light OFF

---

 🧠 Core Logic

```cpp
if(dis_a < 90 && flag1 == 0){
    flag1 = 1;
    if(flag2 == 0){
        person++;
    }
}

if(dis_b < 90 && flag2 == 0){
    flag2 = 1;
    if(flag1 == 0){
        person--;
    }
}
```

---

 📟 Output Display

LCD shows real-time status:

```
Have Person: X
Light is ON / OFF
```

---

 🧪 How It Works

* Ultrasonic sensors measure distance using echo time
* Distance formula used:

  ```
  distance = time / 29 / 2
  ```
* Detection threshold is set to **90 cm**
* Flags prevent false or duplicate counting

---

 ▶️ How to Run

1. Open the code in Arduino IDE
2. Connect components as per pin configuration
3. Upload the code to Arduino
4. Power the system
5. Monitor output on LCD and Serial Monitor

---

 📊 Applications

* Smart Room Automation
* Classroom Occupancy Monitoring
* Retail Footfall Tracking
* Automatic Lighting Systems
* Industrial Entry Monitoring

---

 ⚠️ Limitations

* Not ideal for multiple people passing simultaneously
* Requires accurate sensor placement
* Performance may vary with environment

---

 🔮 Future Enhancements

* Cloud integration (IoT dashboards)
* Mobile app monitoring
* AI-based object detection
* Data logging and analytics

---

 📜 License

This project is open-source and available under the MIT License.

---

 👨‍💻 Author

Aryan Singh
