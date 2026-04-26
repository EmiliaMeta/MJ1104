# Henry the Sniffer: Autonomous Solar Car

A miniature autonomous solar-powered car designed to navigate a competition track using only stored solar energy, following a white guiding line with infrared sensors.

The final prototype successfully completed the track and **won the Lightest Vehicle category** at 166.95 g.

> Group project for course MJ1104 — Practical Introduction to Mechanical Engineering at KTH.  
> **My contributions:** Arduino firmware, testing, and project report.

---

## System Overview

The car uses a solar panel to charge supercapacitors, which then power the motors and electronics — allowing it to drive through both illuminated and dark sections of the track without interruption.

**Key design principle:** The solar panel itself serves as the structural chassis, eliminating the need for a separate frame and minimizing weight.

---

## Hardware Components

| Component | Purpose |
|-----------|---------|
| Solar panel | Primary energy source and structural base |
| Supercapacitors | Store energy for dark track sections |
| Arduino | Controls sensors and motors |
| H-bridge motor driver | Controls motor direction |
| IR sensors (FC51) x2 | Detect white guiding line |
| DC motors x2 | Drive the wheels |
| 3D printed PLA wheels | Lightweight locomotion |

---

## How It Works

**Navigation** uses skid-steering — each motor drives one wheel independently:
- Left sensor detects line → right motor activates (steers left)
- Right sensor detects line → left motor activates (steers right)

Only one motor runs at a time, as the solar panel cannot supply enough instantaneous current for both simultaneously.

**Firmware** written in C++ for Arduino:
```cpp
setup()
  // Initialize sensors and motors
  // Wait 20s for capacitor charging

loop()
  // Read IR sensor values
  // Activate corresponding motor
  // Steer back toward line
```

The 20-second startup delay ensures the capacitors are sufficiently charged before the vehicle starts moving.

---

## Results

| Metric | Value |
|--------|-------|
| Vehicle weight | 166.95 g |
| Track completion | Successful |
| Award | Lightest Vehicle |

---

## Key Engineering Decisions

- **Solar panel as chassis** — reduced component count and total mass
- **Single-motor-at-a-time driving** — worked around power limitations of the solar panel
- **Thicker four-spoke wheels** — solved early deformation issues under load

---

## Team

Daniel Fischer · Melker Gardby · **Emilia Lindqvist** · Carl Julius Mård Danestad · Oscar Olheden · Marcus Stadig · Johannes Toffia

---

## Author

**Emilia Lindqvist** — KTH Information Technology  
[GitHub Profile](https://github.com/EmiliaMeta)
