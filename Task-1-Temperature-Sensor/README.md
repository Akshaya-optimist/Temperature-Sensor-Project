# Temperature Sensor Monitoring – Task 1

This is Task 1 for my Embedded Systems Internship at CodTech.

## 🔧 Project Overview
- *Sensor Used*: TMP Analog Temperature Sensor (Tinkercad)
- *Platform*: Arduino UNO
- *Display*: Serial Monitor
- *Tool*: Tinkercad Simulation

## 📷 Circuit Diagram
![Circuit Diagram](https://github.com/Akshaya-optimist/Embedded-Systems-Internship-Tasks/blob/main/Task-1-Temperature-Sensor/Screenshot%202025-07-19%20163902.png?raw=true)

## 📜 Code
```cpp
const int sensorPin = A0;
float voltage, temperature;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int reading = analogRead(sensorPin);
  voltage = reading * (5.0 / 1023.0);       // Convert analog reading to voltage
  temperature = (voltage - 0.5) * 100.0;    // Convert voltage to Celsius

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");

  delay(1000);  // Wait 1 second
}

