---
layout: page
title: Intelligent Fridge System
description: AIoT-based smart refrigerator with food tracking, expiry alerts, and AI-powered recipe suggestions
img: assets/img/Intelligent_Fridge_featured.png
importance: 2
category: work
date: 2023-07-25
tags:
  - Food management
  - Environment monitoring
  - Recipe suggestion
---

## Group Members

- **Students**: Hao Xizhe (SUSTech), Sun Quanen (UESTC), Wang Gengnan (BUPT), Hong Shiwei (SCU)
- **Professor**: Tan Wee Kek (NUS)
- **Teaching Assistants**: Wu Haiyang, Li Xin (NUS)

## Project Overview

The Smart Refrigerator leverages **AIoT (Artificial Intelligence of Things)** principles to monitor and manage refrigerator contents. With this system, users can track food freshness, receive warnings on expired items, and access recommendations for food usage based on fridge contents.

### Why We Do This Project:

In today’s fast-paced world, food waste has become a growing concern, and many households struggle with managing food storage effectively. Our project aims to address these challenges by:

- **Reducing Food Waste**: Proactively tracking expiration dates and providing timely alerts to prevent spoilage.
- **Promoting Sustainability**: Optimizing food usage with AI-powered recipe suggestions, encouraging users to consume available ingredients efficiently.
- **Enhancing User Convenience**: Automating inventory management to save time and effort, making food management smarter and simpler.

With these goals, the Smart Refrigerator delivers a blend of convenience, sustainability, and innovation, ensuring smarter food management for households and businesses alike.

## 0. Poster Download

📄 **[Download the Project Poster](/assets/img/projects/fridge/Poster_intelligent_fridge.pdf)**

## 1. System Roadmap and Core Functionalities

The system is built on a **Raspberry Pi** platform, integrated with sensors and AI-based predictions for real-time monitoring.

### Core Sensors and Functions:

- **Environmental Monitoring**: Tracks temperature, humidity, and door status using sensors.
- **Food Inventory Management**: Provides real-time updates on stored food, including weight and freshness predictions.
- **Proactive Alerts**: Sends warnings for expired items or abnormal environmental conditions.
- **AI-Driven Suggestions**: Recommends recipes based on available ingredients.

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/Roadmap.png" alt="System Roadmap" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 1: System architecture with AI and IoT integration</figcaption>
</figure>

## 2. Hardware Components

The hardware setup is designed to ensure seamless integration and functionality:

- Sensors collect environmental and food-related data.
- Data is transmitted to the Raspberry Pi through ESP32 and Micro:bit modules.
- The Raspberry Pi acts as the central processing hub, analyzing data and interfacing with the AI and web-based components.

### Key Sensors and Modules:

1. **Environmental Sensors**:

   - **DHT11**: Measures temperature and humidity to ensure optimal storage conditions for food items.
   - **HC-SR04**: Ultrasonic sensor for detecting door status and measuring distances.
   - **Passive Buzzer and RGB LED**: Provide visual and auditory alerts for warnings, such as when the refrigerator door remains open.
   - **Weight Sensor (HX711)**: Collects weight data of stored food items with precision, enabling effective inventory management.

2. **Image Capture and Processing**:

   - **Pi Camera**: Captures images of food items for further processing and classification using AI models.

3. **Communication Modules**:
   - **ESP32**: Gathers sensor data (temperature, humidity, door status) and transmits it to the Raspberry Pi via MQTT protocol for real-time monitoring and warnings.
   - **Micro:bit Modules**: Enable **serial** and **radio communication** for capturing, weighing, and managing inventory.

---

## 3. Artificial Intelligence Integration

The Smart Refrigerator uses a **Pre-trained YOLOv8 model** to assess food expiration and predict freshness. The Raspberry Pi’s AI capabilities enable real-time predictions with high accuracy, evaluated through:

- **Confusion Matrix** and **F1-Confidence Curve** to track prediction performance.

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/Confusion Matrix.png" alt="Confusion Matrix" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 2: Confusion Matrix for YOLOv8 Model</figcaption>
</figure>

<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/F1-Confidence Curve.png" alt="F1-Confidence Curve" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 3: F1-Confidence Curve Showing Model Performance</figcaption>
</figure>

### AI Model Workflow

The AI integration follows a step-by-step roadmap to achieve accurate and real-time predictions:

1. **Step 0: Pre-trained AI Model on PC**  
   A YOLOv8 model is pre-trained on a labeled dataset of various food categories to detect and classify food items accurately.

2. **Step 1: Pi Camera Capture**  
   The Raspberry Pi utilizes the Pi Camera to capture real-time images of food items stored in the refrigerator.

3. **Step 2: AI Predictions on Raspberry Pi**  
   YOLOv8 is deployed on the Raspberry Pi for on-device inference. It detects food items, classifies them into predefined categories, and predicts the freshness.

4. **Step 3: Weight Information Collector**  
   The system correlates weight data collected via the HX711 sensor with the visual classification to ensure precise inventory management.

5. **Step 4: Update Data on Web Database**  
   The classified food data and weight measurements are stored in a cloud-based web database for further analysis and user access.

### Valid Predictions

The YOLOv8 model effectively detects and classifies food items in real-time. The **validation predictions** show:

- Successful identification of common food items like apples, bananas, carrots, and fish with high confidence levels.
- Bounding boxes accurately localize each item in the images, enabling precise tracking.
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/YOLOv8_food_example.png" alt="Validation Predictions" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 4: Validated YOLOv8 predictions for some food items.</figcaption>
</figure>

---

## 4. Web Interface and Database Management

The system features a **web-based interface** that allows users to interact with the Smart Refrigerator's data.

### Features of the Web Interface

1. **Dynamic Dashboard**:

   - Displays real-time data on:
     - Environmental conditions (temperature, humidity).
     - Fridge door status (open/closed).
     - Alerts for expiring or expired food items.
   - Powered by **HTML, CSS, and JavaScript** for a responsive and interactive experience.

2. **Food Inventory Management**:

   - Lists stored food items along with weight, timestamp, and expiration status.
   - Allows users to:
     - Add or remove items from the inventory.
     - View item-specific storage recommendations (e.g., temperature, shelf life).

3. **AI-Powered Recipe Suggestions**:

   - Leverages **ChatGPT** to provide recipe recommendations based on available ingredients.
   - Recipes are dynamically generated using inventory data and a predefined recipe rule set.

4. **User-Friendly Alerts**:
   - Sends notifications for:
     - Food nearing expiration.
     - Abnormal fridge conditions (e.g., high temperature or humidity).
   - Uses visual cues (color-coded indicators) for quick recognition of issues.

#### Key Pages

1. **Index Page**: Provides an overview of fridge contents, environmental conditions, and food expiration warnings.
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/Index_page.png" alt="Index Page" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 5: Web Interface - Index Page showing fridge contents and expiration alerts.</figcaption>
</figure>

2. **Table List Page**: Displays stored food data, including weight, names, and timestamps.
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/Data_page.png" alt="Table List Page" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 6: Table list displaying detailed storage data.</figcaption>
</figure>

3. **ChatGPT Recommendation Page**: Generates recommendations for recipes or meals based on available fridge ingredients.
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="/assets/img/projects/fridge/Recommendation_page.png" alt="Recommendation Page" style="width: 85%; margin: 0 auto;">
  <figcaption style="font-size: 14px; color: gray;">Figure 7: Recommendations based on current ingredients.</figcaption>
</figure>

---

## References

1. Black Dashboard Template: [Link](https://demos.creative-tim.com/black-dashboard-flask/docs/1.0/plugins/chart-js.html)
2. Food Library: [Link](https://www.realsimple.com/food-recipes/shopping-storing/freezing/how-long-food-last-freezer)
3. YOLOv8 Documentation: [Link](https://docs.ultralytics.com/models/yolov8/#supported-modes)
4. Aheleroff S, et al. IoT-enabled smart appliances under Industry 4.0. Advanced Engineering Informatics, 2020.
5. Basa J J A, et al. Smart inventory management system. arXiv, 2019.

---

<!--more-->
