# 🚀 Line-Follower Robot

## 📝 Overview
This repository contains the *Arduino code and documentation* for the Line-Follower Robot, developed as part of the *Ardubotics Workshop* at Esparx, JNTUK. The project involves building and programming a robot that autonomously follows a line using *IR sensors and motor drivers*.

---

## 📦 Features
✅ Autonomous *line-following* capability  
✅ Uses *IR sensors* for obstacle detection  
✅ *L293D motor driver* for efficient movement  
✅ *Customizable* Arduino-based control logic  
✅ Simple yet effective *hardware-software* integration  

---

## 🛠 Hardware Requirements
### 🏗 Components Needed:
- 🔹 *Arduino (ATmega328-based board)*
- 🔹 *L293D Motor Driver IC*
- 🔹 *IR Sensors (Left & Right)*
- 🔹 *DC Motors & Wheels*
- 🔹 *Chassis for the robot*
- 🔹 *Power Supply (Battery or Adapter)*
- 🔹 *USB-to-TTL Serial Converter*
- 🔹 *Connecting Wires & Soldering Kit*

---

## 📡 Circuit Diagram
(Add an image of the circuit diagram here)

*Connections:*
| Component | Arduino Pin |
|-----------|------------|
| Left IR Sensor | A0 |
| Right IR Sensor | A1 |
| Motor Driver enA | 10 |
| Motor Driver in1 | 9 |
| Motor Driver in2 | 8 |
| Motor Driver in3 | 7 |
| Motor Driver in4 | 6 |
| Motor Driver enB | 5 |

---

## 🔢 Arduino Code
cpp
#define enA 10
#define in1 9
#define in2 8
#define in3 7
#define in4 6
#define enB 5
#define left_IR A0
#define right_IR A1

void setup() {
  Serial.begin(9600);
  pinMode(enA,OUTPUT);
  pinMode(in1,OUTPUT);
  pinMode(in2,OUTPUT);
  pinMode(in3,OUTPUT);
  pinMode(in4,OUTPUT);
  pinMode(enB,OUTPUT);
  pinMode(left_IR, INPUT);
  pinMode(right_IR, INPUT);
  analogWrite(enA,120);
  analogWrite(enB,140);
}

void loop() {
  int left_value= digitalRead(left_IR);
  int right_value= digitalRead(right_IR);

  if(left_value==1 && right_value == 0) right();
  else if(right_value==1 && left_value ==  0) left();
  else if(right_value==0 && left_value==0) forward();
  else STOP();
}

void right(){
  digitalWrite(in1,LOW); digitalWrite(in2,HIGH);
  digitalWrite(in3,LOW); digitalWrite(in4,HIGH);
}

void left(){
  digitalWrite(in1,HIGH); digitalWrite(in2,LOW);
  digitalWrite(in3,HIGH); digitalWrite(in4,LOW);
}

void STOP(){
  digitalWrite(in1,LOW); digitalWrite(in2,LOW);
  digitalWrite(in3,LOW); digitalWrite(in4,LOW);
}

void forward(){
  digitalWrite(in1,HIGH); digitalWrite(in2,LOW);
  digitalWrite(in3,LOW); digitalWrite(in4,HIGH);
}


---

## 🔌 Uploading the Code
1. *Install Arduino IDE 1.8.5+*.
2. *Connect Arduino to PC* via USB.
3. *Select Board:* Arduino Uno / ATmega328.
4. *Choose COM Port* from Arduino IDE.
5. *Upload Code* and test robot behavior.

---

## 📺 Project Demonstration
🎥 Watch the robot in action:  
- [📹 Video 1](https://drive.google.com/file/d/1U1U0USihnqO0-vsMsb2RHyNI4mw-tjxb/view?usp=sharing)  
- [📹 Video 2](https://drive.google.com/file/d/1BHB_gPRUpsYaS5u8NYwRIVQVcbwF1PH9/view?usp=sharing)  

---

## 📖 Workshop Summary
The *Ardubotics Workshop* at Esparx, JNTUK was conducted in collaboration with *Zeekers Pvt. Ltd.*. This hands-on session helped students:
- Understand *robotics and automation*.
- Build and program an *autonomous robot*.
- Learn *sensor integration and motor control*.
- Gain *practical soldering and circuit-building* experience.

*Report By:* 🏆 Kowshik Sai Raghav Penumarthi (ECE Dept.)

---

## 🏆 Acknowledgments
Special thanks to *Esparx, JNTUK, **Zeekers Pvt. Ltd.*, and the workshop trainers for their valuable guidance.

---

## 📜 License
This project is *open-source* and available for modification & enhancement! 🚀

Feel free to contribute, suggest improvements, or fork the repository! 🛠✨
