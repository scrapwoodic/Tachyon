# Tachyon
A modular, open-source motorcycle dashboard and telemetry display based on the ESP32-S3 and LVGL

🌌 Tachyon

A lightweight, hyper-customizable navigation and telemetry OS for motorcycles and EVs.

Built for the [GC9A01 1.28" Round Display]

🚀 What is Tachyon?

Tachyon is a bare-metal, modular operating system designed to turn ultra-low-cost microcontrollers into premium, buttery-smooth motorcycle dashboards.

OEM dash pods (like the Royal Enfield Tripper) are locked down and cannot be customized. Aftermarket solutions are either prohibitively expensive or look like bulky tablets clamped to your handlebars.

Tachyon bridges the gap. It is a highly optimized, open-source framework that leverages dual-core processing (FreeRTOS) and the LVGL graphics library to deliver OEM-grade turn-by-turn navigation, real-time clock syncing, and live CAN bus engine telemetry.

🧩 The Modular Ecosystem

Tachyon is built on a modular, physics-inspired architecture. You only compile the modules you need for your specific build.

tachyon — The Core OS. Handles FreeRTOS task scheduling, hardware abstraction, and OTA updates.

tachyon-photon — The UI Renderer. Powered by LVGL, this pushes 60fps gauge animations and dynamic screen transitions to the SPI display.

tachyon-azimuth — The Navigation Engine. A BLE client that parses turn-by-turn routing data from a companion smartphone app via low-energy notification scraping.

tachyon-epoch — The Timekeeper. Handles RTC syncing and beautiful idle clock faces.

tachyon-flux — The Telemetry Core. Interfaces with MCP2515 CAN bus transceivers or OBD2 to read live engine stats (RPM, Temp, Gear Position, Battery Health).

⚙️ Recommended Hardware Stack

Tachyon is optimized for the ESP32-S3 architecture to take advantage of dual cores and high-speed PSRAM (essential for smooth LVGL frame buffers).

The "Cheat Code" Build:

Board: Waveshare ESP32-S3-LCD-1.28 (All-in-one GC9A01 display + ESP32-S3 with 2MB PSRAM + Battery Circuit)

The DIY Build:

Microcontroller: ESP32-S3 SuperMini (or any S3 board with integrated PSRAM)

Display: 1.28" GC9A01 Round TFT LCD (SPI)

Power: 12V to 5V Buck Converter + LC Filter + TVS Diode (for alternator noise suppression)

🛠️ Software Architecture

Environment: PlatformIO (VS Code)

Framework: ESP-IDF / Arduino Core

Graphics: LVGL (Light and Versatile Graphics Library)

Multitasking: FreeRTOS (Core 0: BLE & Telemetry | Core 1: LVGL Renderer)

🗺️ Development Roadmap

[ ] Phase 1: Foundation (Current)

  [ ] SPI Display initialization and PSRAM allocation.

  [ ] FreeRTOS dual-core task splitting.

  [ ] Basic LVGL UI rendering (tachyon-photon).

[ ] Phase 2: Navigation & Time

  [ ] Idle clock faces (tachyon-epoch).

  [ ] Headless Android Companion App (Notification Listener).

  [ ] BLE packet parsing and UI arrow updating (tachyon-azimuth).

[ ] Phase 3: Vehicle Telemetry

  [ ] CAN bus / OBD2 hardware integration.

  [ ] Live RPM and voltage display mapping (tachyon-flux).

  [ ] 3D printed weatherproof enclosure design.

🤝 Contributing

Pull requests are welcome! If you are interested in building custom LVGL gauge themes, optimizing BLE packet delivery, or designing 3D enclosures, feel free to fork the repository and submit a PR.

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.
