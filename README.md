# Automatic Parking System 🚗🔐

This project implements an **automatic parking entry system** using **YOLOv8** for license plate detection, **Tesseract OCR** for plate recognition, and an **Arduino-controlled gate** mechanism triggered by ultrasonic sensing and plate verification.

## 📸 How It Works

1. The system continuously reads frames from a webcam.
2. An ultrasonic sensor detects when a car is near.
3. When a car is close enough:
   - The YOLOv8 model detects the license plate.
   - The plate image is processed and read using OCR.
   - Valid Rwandan plates (e.g., `RAA123B`) are extracted.
4. If a valid plate is detected consistently:
   - The plate number is logged to a CSV file with a timestamp.
   - A command is sent to Arduino to open the gate.
5. After a cooldown period, a new plate can be accepted again.

## 🧠 Features

- 🔍 **YOLOv8 object detection**
- 🔠 **Tesseract OCR for plate recognition**
- 🛂 **Plate format validation** (`RAA123B`)
- 🕓 **Duplicate detection cooldown** (5 minutes)
- 📁 **Logging** to CSV: `plates_log.csv`
- 🔌 **Serial communication with Arduino**
- 🧪 **Mocked ultrasonic sensor for simulation**

## 🛠 Requirements

- Python 3.x
- [YOLOv8](https://github.com/ultralytics/ultralytics)
- OpenCV
- Tesseract OCR installed on Windows
- PyTesseract
- pySerial

## 📦 Installation

```bash
pip install ultralytics opencv-python pytesseract pyserial
