# 🌱 Automatic Plant Irrigation System According To Humidity

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> Hệ thống tưới cây tự động theo độ ẩm đất sử dụng STM32F103C8T6, cảm biến độ ẩm và bơm nước điều khiển bằng relay.  
> This repository contains firmware, simulation and documentation for an STM32-based automatic plant irrigation system.

---

## 1. Overview / Tổng quan

This project implements an **automatic irrigation system** using:

- **STM32F103C8T6** microcontroller  
- **Soil moisture sensor** (analog)  
- **Relay-controlled 12V DC water pump**  
- Optional **LCD / indicators / buttons** for user interaction  

The system automatically waters plants when soil humidity drops below a configurable threshold and stops watering when humidity recovers or a safety timeout is reached.

Dự án hiện thực **hệ thống tưới cây tự động** sử dụng:

- Vi điều khiển **STM32F103C8T6**
- Cảm biến độ ẩm đất dạng tương tự (analog)
- Bơm nước DC điều khiển qua **relay**
- Một số nút nhấn, đèn chỉ thị / LCD (tuỳ chọn)

---

## 2. Features / Tính năng

- 🌧️ **Automatic watering** when soil moisture < threshold  
- ✋ **Manual / Auto modes** via button or switch  
- 💧 **Over-watering protection**: giới hạn thời gian bật bơm liên tục  
- 📊 Optional **humidity and status display** (LCD/OLED)  
- 🔌 Designed for 12V pump with 3.3V MCU supply  

---

## 3. System Architecture / Kiến trúc hệ thống

> (Bạn hãy upload hình block diagram vào `docs/images/system_overview.png` rồi giữ nguyên link dưới.)

![System Block Diagram](docs/images/system_overview.png)

**Main blocks:**

- STM32F103C8T6 MCU
- Soil moisture sensor → ADC input
- Relay + driver → Water pump
- Power supply: 12V adapter + 3.3V regulator
- User interface: LEDs, buttons, optional LCD

---

## 4. Repository Structure / Cấu trúc thư mục

```text
AUTOMATIC-PLANT-IRRIGATION-SYSTEM-ACCORDING-TO-HUMIDITY/
├─ firmware/       # STM32 firmware (Keil uVision project)
│   ├─ Src/
│   ├─ Inc/
│   └─ *.uvprojx
│
├─ simulation/     # Proteus simulation files (.dsn, .pdsprj)
│   └─ irrigation_system.dsn
│
├─ hardware/       # Schematic / PCB files (PDF, images, CAD files)
│   └─ schematic.pdf
│
├─ docs/           # Reports and documents
│   ├─ BTL_TKHTN.pdf
│   ├─ TIEN_DO_10-07.docx
│   └─ images/
│       └─ system_overview.png
│
├─ .gitignore
├─ LICENSE
└─ README.md

