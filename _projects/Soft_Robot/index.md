---
layout: page
title: Caterpillar-inspired Soft Robot
description: Bio-inspired soft robot with PCB-based control system and wireless communication
img: assets/img/Soft_Robot_featured.png
importance: 1
category: work
date: 2024-02-16
tags:
  - PCB design
  - WiFi
  - Bluetooth
---

## Authors

Xizhe Hao<sup>1,2</sup>, Jianzhi Tang<sup>1,3</sup>, Zhiqi Guo<sup>1,4</sup>, Yong Zhu<sup>1_</sup>

<sup>1</sup> Department of Mechanical and Aerospace Engineering, North Carolina State University, Raleigh, NC 26975, USA  
<sup>2</sup> School of System Design and Intelligent Manufacturing, Southern University of Science and Technology, Shenzhen, China  
<sup>3</sup> Weiyang College, Tsinghua University, Beijing, China  
<sup>4</sup> School of Microelectronics, Southern University of Science and Technology, Shenzhen, China

---

## Project Overview

This project presents a bio-inspired soft robot that mimics the locomotion of caterpillars, developed at North Carolina State University. The robot utilizes innovative thermal-driven actuation through liquid crystal elastomer (LCE) actuators and friction modulation to achieve versatile crawling capabilities through programmable control sequences.

The system demonstrates how biomimicry and advanced control systems can create versatile, safe, and efficient robotic solutions for real-world applications in confined spaces, medical devices, and inspection tasks.

## 0. Resources

📄 **[Download the Project Poster](/assets/img/projects/soft_robot/Poster_0215_Gears Program_Final.pdf)**

💻 **[View the GitHub Repository](https://github.com/Xizhe-Hao/Soft-Robotics_control)**

---

## 1. Background and Motivation

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/soft_robot/background.png" alt="Project Background" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 1: Biological inspiration and motivation for soft robot development</figcaption>
</figure>

Soft robotics represents a paradigm shift from traditional rigid robots, offering unique advantages in adaptability and safety. Caterpillars demonstrate remarkable locomotion capabilities through peristaltic motion and friction modulation, making them ideal models for soft robotic systems.

### Project Objectives:

- **Enhancing Mobility in Confined Spaces**: Creating robots that can navigate through narrow passages and irregular terrains where traditional robots struggle
- **Improving Safety in Human Interaction**: Soft materials reduce the risk of injury, making these robots suitable for medical applications and human-robot collaboration
- **Advancing Bio-inspired Engineering**: Learning from nature's solutions (caterpillar locomotion) to develop more efficient and adaptable robotic systems
- **Enabling Untethered Operation**: Implementing wireless control systems for greater autonomy and practical deployment

---

## 2. Overall Design and System Architecture

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/soft_robot/overall_design.png" alt="Overall System Design" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 2: Complete system architecture and design overview</figcaption>
</figure>

The soft robot system integrates three key subsystems: **actuation**, **control**, and **communication**. The design philosophy emphasizes modularity, energy efficiency, and real-time responsiveness.

### Core Components:

- **Thermal Actuation System**: Liquid crystal elastomer (LCE) actuators controlled via resistive joule heating
- **Electronic Control Unit**: Custom PCB with microcontroller and power management circuitry
- **Wireless Communication Module**: Dual-mode (Wi-Fi + Bluetooth) for flexible operation
- **Friction Modulation Mechanism**: Asymmetric surface texture patterns for optimized traction control

---

## 3. Robot Manufacturing and Fabrication

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/soft_robot/Robot manufacturing.png" alt="Robot Manufacturing Process" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 3: Fabrication process and assembly of the soft robot</figcaption>
</figure>

The robot fabrication involves multiple stages:

1. **LCE Actuator Preparation**: Liquid crystal elastomer films are prepared with embedded resistive heating elements
2. **Body Structure Assembly**: Soft body segments are assembled with appropriate spacing for actuation
3. **Surface Texture Application**: Asymmetric friction patterns are applied to enable directional locomotion
4. **Electronics Integration**: PCB control system is integrated with the soft body structure

---

## 4. Electronic Control System and Hardware

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/soft_robot/Control.png" alt="Control System Architecture" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 4: Electronic control system and circuit architecture</figcaption>
</figure>

The hardware architecture is designed for precise control of thermal actuation while maintaining compact size and energy efficiency.

### 4.1 Custom PCB Design

The control board features:

1. **Microcontroller Unit (MCU)**:

   - Processes control algorithms for coordinated multi-phase crawling sequences
   - Manages timing and synchronization of heating elements
   - Interfaces with wireless communication modules

2. **Power Management Circuit**:

   - **NMOS Transistor Switches**: Enable precise current regulation to individual heating elements
   - **PWM Controllers**: Provide variable power delivery for temperature control
   - **Protection Circuits**: Overvoltage and overcurrent protection for safe operation

3. **Sensor Integration**:
   - Temperature feedback sensors for closed-loop thermal control
   - Current sensing for power monitoring and diagnostics

### 4.2 Wireless Communication System

- **Wi-Fi Module (ESP32/ESP8266)**:
  - Remote monitoring of robot status and performance metrics
  - Parameter adjustment and programming of motion sequences
  - Data logging for analysis and optimization
- **Bluetooth Low Energy (BLE)**:
  - Low-latency direct control via mobile devices
  - Minimal power consumption during operation
  - Intuitive mobile app interface for real-time control

### 4.3 Actuation Mechanism Details

1. **Joule Heating System**:

   - Resistive heating elements embedded in or attached to thermally-responsive materials
   - Controlled temperature range: 25°C - 80°C for optimal actuation
   - Response time: ~2-5 seconds per heating/cooling cycle

2. **Shape-Memory Effect**:

   - Materials undergo reversible phase transformation with temperature changes
   - Generates controlled deformation for forward propulsion
   - Recovers original shape upon cooling

3. **Friction Modulation**:
   - Asymmetric surface texture patterns create directional traction
   - Alternating anchoring (high friction) and sliding (low friction) phases
   - Enables net forward displacement during each actuation cycle

---

## 5. Control System and Motion Programming

### 5.1 Control Algorithm

The robot employs a multi-phase control strategy inspired by caterpillar locomotion:

1. **Phase 1 - Anterior Anchoring**: Front section heated, creating grip point
2. **Phase 2 - Posterior Contraction**: Rear section heated, pulling body forward
3. **Phase 3 - Posterior Anchoring**: Rear section grips while front cools
4. **Phase 4 - Anterior Extension**: Front section extends forward, completing cycle

### 5.2 Programmable Gaits

The system supports multiple locomotion modes:

- **Standard Crawl**: Balanced speed and energy efficiency for flat surfaces
- **High-Speed Mode**: Rapid heating cycles for faster movement
- **Climbing Mode**: Extended anchoring phases for inclined surfaces
- **Precision Mode**: Fine-grained control for careful navigation

### 5.3 Thermal Management

- **PWM Control**: Pulse-width modulation enables precise temperature regulation
- **Duty Cycle Range**: 0-100% adjustable for different materials and conditions
- **Thermal Feedback**: Real-time temperature monitoring prevents overheating
- **Energy Optimization**: Adaptive algorithms minimize power consumption

---

## 6. Experimental Results and Performance

### 6.1 Locomotion Characterization

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/soft_robot/Results_A.B.C.png" alt="Experimental Results Part 1" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 5: Locomotion performance analysis including speed, displacement, and gait patterns</figcaption>
</figure>

### 6.2 Performance Under Various Conditions

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/soft_robot/Results_D.E.png" alt="Experimental Results Part 2" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 6: Performance evaluation on different surfaces and environmental conditions</figcaption>
</figure>

### 6.3 Key Performance Metrics

- **Maximum Speed**: 2-5 cm/s (adjustable based on gait selection)
- **Operating Duration**: 30-60 minutes on battery power (depending on actuation frequency)
- **Control Latency**: <100ms for Bluetooth, <200ms for Wi-Fi
- **Surface Adaptability**: Flat, inclined (up to 30°), and rough surfaces

### 6.4 Wireless Control Features

1. **Mobile Application Interface**:

   - Real-time directional control (forward, reverse, pause)
   - Gait pattern selection and customization
   - Performance monitoring (battery, temperature, distance traveled)

2. **Remote Monitoring Dashboard**:
   - Wi-Fi connectivity for remote observation
   - Data logging and visualization
   - Diagnostic alerts and status notifications

### 6.5 Energy Efficiency

- **Optimized Heating Cycles**: Minimize power consumption while maintaining performance
- **Intelligent Duty Cycling**: Automatic adjustment based on load and terrain
- **Standby Mode**: Low-power state during inactivity
- **Battery Management**: Real-time monitoring and alerts for battery status

---

## 7. Applications and Future Directions

### 7.1 Current Applications

This soft robot technology demonstrates potential in:

1. **Medical Devices**:

   - Minimally invasive surgical tools
   - Endoscopic inspection systems
   - Drug delivery mechanisms in confined anatomical spaces

2. **Industrial Inspection**:

   - Pipeline inspection in narrow conduits
   - Equipment diagnostics in hard-to-reach areas
   - Environmental monitoring in hazardous zones

3. **Search and Rescue**:

   - Navigation through debris and rubble
   - Survivor detection in collapsed structures
   - Sample collection in disaster zones

4. **Research and Education**:
   - Platform for studying bio-inspired locomotion
   - Educational tool for soft robotics principles
   - Testbed for control algorithm development

### 7.2 Future Enhancements

Planned improvements include:

- **Advanced Sensors**: Integration of cameras, proximity sensors, and environmental monitors
- **Autonomous Navigation**: AI-powered path planning and obstacle avoidance
- **Multi-Robot Coordination**: Swarm robotics capabilities for collaborative tasks
- **Enhanced Materials**: Development of faster-responding thermal actuators
- **Solar Charging**: Extended operation time through renewable energy integration

---

## 8. Technical Challenges and Solutions

### Challenges Addressed:

1. **Thermal Response Time**:

   - **Challenge**: Slow heating/cooling cycles limit speed
   - **Solution**: Optimized material selection and PWM control strategies

2. **Power Management**:

   - **Challenge**: High current draw from heating elements
   - **Solution**: Efficient switching circuits and duty cycle optimization

3. **Wireless Reliability**:

   - **Challenge**: Maintaining connection during movement
   - **Solution**: Dual-mode communication with automatic failover

4. **Friction Control**:
   - **Challenge**: Achieving directional movement on various surfaces
   - **Solution**: Asymmetric texture design and adaptive gait algorithms

---

## References

1. Wu, S., Hong, Y., Zhao, Y., Yin, J., & Zhu, Y. (2023). Caterpillar-inspired soft crawling robot with distributed programmable thermal actuation. _Science Advances_, 9(12), eadf8014. [https://doi.org/10.1126/sciadv.adf8014](https://doi.org/10.1126/sciadv.adf8014)

2. He, Q., Wang, Z., Wang, Y., Minori, A., Tolley, M. T., & Cai, S. (2019). Electrically controlled liquid crystal elastomer-based soft tubular actuator with multimodal actuation. _Science Advances_, 5(10), eaax5746. [https://doi.org/10.1126/sciadv.aax5746](https://doi.org/10.1126/sciadv.aax5746)

---

## Acknowledgements

Great thanks to the generous assistance from Shuang Wu, Jennifer Lee, and the Nanomechanics and Nanoengineering Laboratory, Department of Mechanical and Aerospace Engineering, NCSU. This small creation could not have been here without their tireless assistance and sharing of resources.

---

<!--more-->
