# Drowsiness-Detection-Application
# 🚗 Drowsiness Detection Android Application

> Real-time drowsiness detection using Eye Aspect Ratio (EAR), facial landmark detection, and an audible alert system.

## 📌 Overview

Drowsiness Detection is an Android application designed to identify prolonged eye closure and provide an immediate alert to the user.

The application uses the smartphone's front camera to monitor the user's face and eyes in real time. The Eye Aspect Ratio (EAR) is used to estimate eye openness. When the EAR remains below a predefined threshold for a specified duration, the system identifies a possible drowsiness event and triggers an alarm.

The application is designed to work offline and does not require additional hardware or continuous internet connectivity.

---

## 🎯 Problem Statement

Drowsiness and fatigue can reduce attention, reaction time, and productivity, particularly during prolonged driving, machinery operation, and other activities requiring continuous concentration.

Many existing monitoring systems depend on specialized hardware, wearable sensors, or expensive equipment.

This project aims to provide a lightweight and accessible smartphone-based solution using the device's existing front camera.

---

## 💡 Proposed Solution

The application continuously monitors the user's facial features and eye movements.

The detection pipeline is:

Camera Input
      ↓
Face Detection
      ↓
Eye Landmark Detection
      ↓
EAR Calculation
      ↓
Eye Closure Analysis
      ↓
Drowsiness Detection
      ↓
Alarm Trigger

If the user's eyes remain closed beyond the configured duration, the application triggers an audible alert.

---

## 🔬 Eye Aspect Ratio (EAR)

Eye Aspect Ratio is used to measure the degree of eye openness.

A simplified representation is:

EAR = (||p2-p6|| + ||p3-p5||) / (2 × ||p1-p4||)

where the points represent landmarks around the eye.

When the eyes close, the vertical distances decrease and the EAR value decreases.

The application monitors the EAR over time rather than treating every short blink as drowsiness.

---

## ✨ Features

- 📷 Real-time front-camera monitoring
- 👁️ Eye-state monitoring
- 📊 Eye Aspect Ratio based detection
- 🚨 Audible drowsiness alarm
- ⏱️ Eye-closure duration threshold
- 📱 Android application
- 🌐 Offline operation
- 🔊 Configurable alarm/sensitivity
- ⚡ Lightweight real-time monitoring
- 🎥 Continuous camera-based detection

---

## 🏗️ System Architecture

```text
                Smartphone Front Camera
                         │
                         ▼
                  Camera Input
                         │
                         ▼
                   Face Detection
                         │
                         ▼
                Eye Landmark Detection
                         │
                         ▼
                   EAR Calculation
                         │
                         ▼
              Eye Closure Duration Check
                         │
                 ┌───────┴───────┐
                 │               │
             Normal            Drowsy
                 │               │
                 ▼               ▼
            Continue         Trigger Alarm
            Monitoring            │
                                  ▼
                            User Alert
