<p style="font-size: 40px;">RFID-Based Attendance System Using ESP8266 with Google Sheets</p>

<b>📌 Overview </b>

<b>This project is an IoT-based Smart Attendance System that uses an ESP8266 NodeMCU and RC522 RFID Reader to automatically record attendance and store it in Google Sheets in real time. The system eliminates manual attendance, reduces errors, and provides instant cloud-based record management.</b>

<b>🚀 Features</b>

<b>- RFID card-based attendance marking
- Real-time data logging to Google Sheets
- Wi-Fi connectivity using ESP8266 NodeMCU
- Automatic date and time recording
- LCD display for user feedback
- Buzzer indication for successful scans
- Cloud-based attendance storage
- Low-cost and easy-to-deploy solution</b>

<b>🛠️ Hardware Components</b>

<b>Component| Quantity
NodeMCU ESP8266| 1
RC522 RFID Reader| 1
RFID Tags/Cards| As Required
I2C LCD Display (16x2)| 1
Buzzer| 1
Jumper Wires| As Required
Breadboard| 1</b>

<b>🔧 Software Requirements</b>

<b>- Arduino IDE
- ESP8266 Board Package
- Google Sheets
- Google Apps Script</b>

<b>Required Libraries</b>

<b>ESP8266WiFi.h
WiFiClientSecure.h
SPI.h
MFRC522.h
LiquidCrystal_I2C.h</b>

<b>⚙️ Working Principle</b>

<b>1. User scans an RFID card.
2. RC522 reads the unique UID of the card.
3. ESP8266 verifies the card information.
4. Attendance data is sent to Google Apps Script through Wi-Fi.
5. Google Apps Script stores the data in Google Sheets.
6. LCD displays attendance status.
7. Buzzer confirms successful attendance marking.</b>

<b>🔌 Circuit Connections</b>

RC522 → NodeMCU

RC522| NodeMCU
SDA| D8
SCK| D5
MOSI| D7
MISO| D6
RST| D3
GND| GND
3.3V| 3.3V

LCD (I2C) → NodeMCU

LCD| NodeMCU
SDA| D2
SCL| D1
VCC| 5V
GND| GND

Buzzer

Buzzer| NodeMCU
+| D4
-| GND

<b>📊 Google Sheets Integration</b>

<b>The attendance records are automatically stored in Google Sheets with:</b>
<th>- Student Name</th>
<th>- RFID UID</th>
<th>- Date</th>
<th>- Time In</th>
<th>- Time Out</th>
<th>- Working Hours</th>

<b>Google Apps Script acts as a web service between ESP8266 and Google Sheets. Real-time synchronization allows attendance monitoring from anywhere.</b>

<b>📁 Project Structure</b>

<b>RFID-Attendance-System/</b>

├── RFID_Attendance.ino
├── GoogleAppsScript.js
├── Circuit_Diagram.png
├── Images/
├── README.md
└── Libraries/

<b>🎯 Applications</b>

<b>- Schools and Colleges
- Employee Attendance Monitoring
- Office Entry Systems
- Laboratories
- Libraries
- Smart Campus Projects</b>

<b>📈 Future Enhancements</b>

<b>- Face Recognition Integration
- Mobile App Dashboard
- Email Notifications
- Cloud Database Support
- ESP32 Upgrade
- Attendance Analytics Dashboard</b>

<b>📷 Project Images</b>

<b>Add screenshots of:</b>

- Circuit Diagram
- Hardware Setup
- Google Sheets Output
- Attendance Scan Process

<b>🤝 Contribution</b>

<b>Contributions, suggestions, and improvements are welcome. Feel free to fork the repository and create a pull request.</b>

<b>📜 License</b>

<b>This project is released under the MIT License.</b>

<b>👨‍💻 Author</b>

<b>Vivek Kumbar</b>
<b>ECE Student | IoT & Embedded Systems Enthusiast</b>

<b>If you found this project useful, please ⭐ star this repository.</b>
