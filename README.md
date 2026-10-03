# IoT-Based Attendance System using ESP8266 and Google Sheets

An IoT attendance system that captures attendance with an **ESP8266 Wi-Fi module** and logs it in real time to a **Google Sheet**. No manual entry, no paper registers, and records are accessible from anywhere.

## Features

- Automatic attendance capture with timestamp
- Real-time upload to Google Sheets over Wi-Fi
- Cloud storage, so data is viewable and exportable anytime
- Low-cost and easy to build
- Easily extendable (more users, more devices, notifications)

## How It Works

```
[Input device] --> [ESP8266] --Wi-Fi--> [Google Apps Script Web App] --> [Google Sheet]
```

1. A user identifies themselves (e.g., RFID card scan).
2. The ESP8266 reads the ID and connects to Wi-Fi.
3. It sends the ID to a Google Apps Script web app via HTTPS.
4. The script appends the ID, name, date, and time as a new row in the sheet.

## Hardware Required

| Component | Qty |
|---|---|
| ESP8266 (NodeMCU / ESP-01) | 1 |
| RFID reader (RC522) + tags/cards | 1 |
| Buzzer / LED (optional feedback) | 1 |
| 16x2 I2C LCD (optional) | 1 |
| Jumper wires, breadboard | as needed |
| 5V power supply / USB cable | 1 |

> Update this table to match the input device you actually use (RFID, fingerprint, keypad, etc.).

## Software Required

- Arduino IDE with ESP8266 board package
- Libraries: `ESP8266WiFi`, `ESP8266HTTPClient`, `WiFiClientSecure`, `MFRC522`
- Google account (Google Sheets + Apps Script)

## Circuit Connections (NodeMCU + RC522)

| RC522 | NodeMCU |
|---|---|
| SDA (SS) | D4 |
| SCK | D5 |
| MOSI | D7 |
| MISO | D6 |
| RST | D3 |
| 3.3V | 3V3 |
| GND | GND |

## Setup

### 1. Google Sheet

1. Create a new Google Sheet.
2. Add headers in row 1: `Date | Time | ID | Name | Status`

### 2. Google Apps Script

1. In the sheet, go to **Extensions > Apps Script**.
2. Paste the following:

```javascript
function doGet(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var now = new Date();
  var date = Utilities.formatDate(now, "Asia/Kolkata", "dd/MM/yyyy");
  var time = Utilities.formatDate(now, "Asia/Kolkata", "HH:mm:ss");
  var id = e.parameter.id;
  var name = e.parameter.name || "Unknown";
  sheet.appendRow([date, time, id, name, "Present"]);
  return ContentService.createTextOutput("OK");
}
```

3. Click **Deploy > New deployment > Web app**.
4. Set *Execute as*: **Me**, *Who has access*: **Anyone**.
5. Copy the **Web App URL**.

### 3. ESP8266 Firmware

1. Open the `.ino` file in Arduino IDE.
2. Edit the credentials:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";
String scriptURL = "https://script.google.com/macros/s/YOUR_DEPLOYMENT_ID/exec";
```

3. Select **Board: NodeMCU 1.0 (ESP-12E)** and the correct COM port.
4. Upload the code.

## Usage

1. Power the device and wait for the Wi-Fi connection.
2. Scan a card/tag.
3. The attendance row appears in the Google Sheet within a few seconds.

## Project Structure

```
.
├── firmware/
│   └── attendance.ino
├── google-apps-script/
│   └── Code.gs
├── docs/
│   └── circuit-diagram.png
└── README.md
```

## Future Improvements

- Name lookup from a registered-users sheet
- Duplicate-scan prevention
- Offline buffering when Wi-Fi is down
- Telegram/email notification for absentees
- Dashboard with attendance analytics

## Security Note

Do not commit your Wi-Fi password or Apps Script deployment URL to a public repository. Keep them in a separate `secrets.h` file and add it to `.gitignore`.

## License

MIT License. Free to use and modify.

## Author

**Vivek**, Electronics and Communication Engineering
