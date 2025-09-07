# Roadrunner Telemetry

Ein Elektronikprojekt zur Geschwindigkeits- und Beschleunigungsmessung auf Basis des  
[LILYGO® T-Display-S3 (ESP32-S3)](https://github.com/Xinyuan-LilyGO/T-Display-S3)  
und des **Beitian BN-880 GNSS/Kompass**.

## Ziele
- **Section Control**: Durchschnittsgeschwindigkeit messen ab Tastendruck (Start/Stop).  
- **Beschleunigungsmessung**: Zeiten für 0–50 km/h und 0–100 km/h.  
- **Live-Anzeige**: Geschwindigkeit, GNSS-Status, Fix-Qualität, Messzustand.  
- **Robuste Bauweise**: Wasserdichtes 3D-gedrucktes Gehäuse (IP67/68), automotive-taugliche Verdrahtung.  
- **Erweiterbarkeit**: Modularer Code, zusätzliche Features (Akkubetrieb, Logging, Sensoren).

## Hardware
- LILYGO® T-Display-S3 (ESP32-S3)  
- Beitian BN-880 GNSS + Kompass  
- 2× Taster (IP67, Start/Stop Section-Control, Start Beschleunigungsmessung)  
- Kabel, Schrumpfschlauch, Zugentlastung, Lötzubehör  
- Optional: Step-Down Wandler (12V→5V), Akku mit Fuel-Gauge, SD-Speicher

## Software
- [PlatformIO](https://platformio.org/) + Arduino-Framework  
- Modularer Aufbau:
  - `drivers/` → GNSS, Kompass, Buttons  
  - `services/` → Fix-Filter, Section Control, 0–X Timer, Glättung, Logging  
  - `ui/` → Display-Anzeige  
  - `include/config.h` → Pin-Zuordnung, Grenzwerte

## Dokumentation
- Board-Doku: [LILYGO T-Display-S3 Repo](https://github.com/Xinyuan-LilyGO/T-Display-S3)  
- GNSS-Datenblatt: Beitian BN-880  
- Eigene Notizen: `doc/notes.md`  

## To-do
- [ ] Erste Verdrahtung BN-880 ↔ T-Display-S3 + Taster  
- [ ] Basis-Testcode (UART + PPS + Taster-Ausgabe)  
- [ ] GNSS-Parser (Geschwindigkeit, Fix-Qualität, HDOP)  
- [ ] UI mit Geschwindigkeit in großer Schrift  
- [ ] Section-Control Zustandsmaschine  
- [ ] 0–50 und 0–100 Timer  
- [ ] Gehäuse-Design (3D, IP67)  

---

⚡ Projektstatus: **In Arbeit** – USB-Versorgung für erste Tests, Akku & Fuel-Gauge später als Erweiterung.
