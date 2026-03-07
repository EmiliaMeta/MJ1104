# Henry the Sniffer -- Supercharged Solar Car Driving in Dark

## Project Overview

**Henry the Sniffer** is a miniature autonomous solar-powered car
developed as part of the course **MJ1104 -- Practical Introduction to
Mechanical Engineering** at the **Royal Institute of Technology (KTH)**.

The project focused on designing and constructing an **energy‑efficient
solar car** capable of navigating a track with obstacles and curves
using only **stored solar energy**. The car was required to operate in
both **light and dark sections** of the track and follow a **white
guiding line** using infrared sensors.

The project combined **mechanical design, electronics, and embedded
programming** to produce a working prototype that could compete in
several design and performance categories.

The final prototype successfully navigated the competition track and
**won the category for the lightest vehicle**.

------------------------------------------------------------------------

# Project Goals

The primary goal of the project was to design a **fully functional
solar-powered miniature vehicle** that could:

-   Navigate a predefined track from start to finish
-   Follow a white guiding line using sensors
-   Operate in both illuminated and dark sections of the track
-   Run exclusively on **stored solar energy**
-   Maintain **minimal weight** for efficiency

The team specifically aimed to compete in the categories:

-   Lightest Vehicle
-   Eco Design

------------------------------------------------------------------------

# System Overview

The vehicle consists of the following core components:

-   Solar panel (primary energy source)
-   Supercapacitors for energy storage
-   Arduino microcontroller
-   Two DC motors with gearbox
-   Motor controller (H‑bridge)
-   Two IR sensors (FC51)
-   Custom 3D‑printed wheels and support structure

The **solar panel charges capacitors**, which then power the electronics
and motors during operation, allowing the car to drive even through dark
sections of the track.

------------------------------------------------------------------------

# Hardware Components

  Component                 Purpose
  ------------------------- ---------------------------------------
  Solar panel               Converts light into electrical energy
  Capacitors                Store electrical energy
  Arduino microcontroller   Controls sensors and motors
  Motor driver (H‑bridge)   Controls motor direction
  IR sensors (FC51)         Detect the white line on the track
  DC motors                 Drive the wheels
  3D printed wheels         Provide lightweight locomotion

------------------------------------------------------------------------

# Vehicle Design

A key design principle was **extreme weight reduction**.\
Instead of building a traditional chassis, the **solar panel itself acts
as the structural base**.

Advantages of this design:

-   Lower total mass
-   Fewer components
-   Improved energy efficiency
-   Simpler construction

Additional features:

-   Custom **PLA 3D‑printed wheels**
-   A **rounded support pin** at the rear to stabilize the vehicle
-   Components mounted directly onto the solar panel using lightweight
    adhesives

------------------------------------------------------------------------

# Steering and Navigation

The car uses a **skid‑steering system**.

This means:

-   Each motor drives one wheel
-   Only one motor runs at a time
-   The vehicle alternates between motors to follow the line

Two **IR sensors** detect the white line on a black surface.

Behavior:

-   If the **left sensor detects the line**, the right motor activates
-   If the **right sensor detects the line**, the left motor activates

This causes the car to steer back toward the line.

------------------------------------------------------------------------

# Software

The vehicle is programmed using **Arduino (C/C++)**.

The program performs the following tasks:

1.  Waits for capacitor charging at startup
2.  Continuously reads sensor values
3.  Activates motors depending on sensor input
4.  Adjusts direction to keep the vehicle on the track

Example structure:

    setup()
      initialize sensors and motors
      wait for capacitor charging

    loop()
      read sensors
      determine direction
      activate corresponding motor

------------------------------------------------------------------------

# Key Engineering Considerations

### Weight Optimization

Reducing weight was critical for maximizing energy efficiency.\
Minimal material usage and compact component placement were prioritized.

### Energy Management

The solar panel cannot provide sufficient instantaneous current to drive
both motors simultaneously. Therefore the system drives **only one motor
at a time**.

### Mechanical Durability

Early wheel prototypes deformed due to load and acceleration forces.\
The final design used **thicker four‑spoke wheels** to increase
strength.

### Charging Delay

A **20‑second startup delay** was implemented to allow capacitors to
charge before the vehicle begins moving.

------------------------------------------------------------------------

# Results

During the final competition:

-   Vehicle weight: **166.95 g**
-   Successfully completed the track
-   Won the category **Lightest Vehicle**

The vehicle performed reliably but required longer charging time before
driving due to the low power output of the solar panel.

------------------------------------------------------------------------

# Lessons Learned

The project provided experience in:

-   Mechanical design and prototyping
-   Embedded systems programming
-   Sensor integration
-   Energy-efficient engineering
-   Team-based engineering workflows

The main takeaway was that **simplicity and weight reduction can
significantly improve system efficiency**, especially when working with
limited energy sources.

------------------------------------------------------------------------

# Team Members

-   Daniel Fischer\
-   Melker Gardby\
-   Emilia Lindqvist\
-   Carl Julius Mård Danestad\
-   Oscar Olheden\
-   Marcus Stadig\
-   Johannes Toffia

KTH -- Mechanical Engineering Programme

------------------------------------------------------------------------

# Course Information

Course: **MJ1104 -- Practical Introduction to Mechanical Engineering**\
Institution: **KTH Royal Institute of Technology**\
Year: **2024**
