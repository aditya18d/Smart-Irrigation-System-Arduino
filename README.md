# 🌱 Smart Irrigation System using Arduino Uno

An automated irrigation system that controls water supply based on real-time soil moisture
levels using Arduino Uno. This project helps reduce water wastage and enables efficient
irrigation for small-scale farming and gardening.

---

## 📌 Problem Statement
Traditional irrigation systems rely on manual control or fixed schedules, which often leads
to overwatering or underwatering. This results in water wastage and affects crop health.

---

## ✅ Solution
This Smart Irrigation System uses a soil moisture sensor to continuously monitor soil
conditions. Based on the sensor readings, the Arduino automatically turns the water pump
ON or OFF using a relay module.

---

## 🛠️ Components Used
- Arduino Uno
- Soil Moisture Sensor
- Relay Module
- DC Water Pump
- Jumper Wires
- 5V Power Supply
- USB Cable

---

## ⚙️ Working Principle
1. Soil moisture sensor measures the moisture level of the soil.
2. Arduino reads analog sensor values.
3. If soil is dry → Pump turns ON.
4. If soil is sufficiently wet → Pump turns OFF.
5. The process runs continuously without manual intervention.

---

## 🔁 Algorithm
1. Initialize Arduino pins.
2. Read soil moisture sensor value.
3. Compare value with threshold.
4. Turn pump ON if moisture is low.
5. Turn pump OFF if moisture is high.
6. Repeat continuously.

---

## 💻 Arduino Code
```cpp
int soil_sensor = 0;

void setup() {
  pinMode(A0, INPUT);
  pinMode(7, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  soil_sensor = analogRead(A0);
  Serial.println(soil_sensor);

  if (soil_sensor < 100) {
    digitalWrite(7, HIGH);  // Pump ON
  } else {
    digitalWrite(7, LOW);   // Pump OFF
  }

  delay(1000);
}
