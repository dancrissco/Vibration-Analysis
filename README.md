# Vibration-Analysis
Vibration Analysis with MG24
# 🌀 Vibration Analysis with XIAO MG24 Sense (IMU + Mic)

### Off-the-Shelf Starter Course for Predictive Maintenance, Machine Health, and Acoustic-Vibration Fusion

---

## 🎯 Objective
Learn to capture, visualize, and interpret machine vibration and sound using only the **Seeed Studio XIAO MG24 Sense**.  
No custom PCB or special fixture required — just an off-the-shelf XIAO case, a USB cable, and a power source.

---

## 🧰 Hardware Setup

| Component | Description | Source |
|------------|--------------|--------|
| Seeed XIAO MG24 Sense | Built-in 6-axis IMU + PDM mic | Seeed Studio |
| Off-the-shelf XIAO case | Vent-slot grill above mic | Arduino / Seeed |
| USB-C → A cable | Braided or regular | Common |
| Mobile power bank | Dual-port, 5 V 1 A min | Any brand |
| Blue painter’s tape / mount pad | Temporary surface mount | Hardware store |

**Assembly:**  
Connect the MG24 to the case, plug into power bank, and affix to a vibrating surface (fan, pump, motor housing) using blue tape for quick experiments.

---

## 💻 Software Stack

- **Arduino IDE** for firmware upload  
- **Node-RED Dashboard 2.0** for live monitoring  
- **Python 3.10+** (NumPy, SciPy, pandas, matplotlib) for analysis  
- *(Optional)* TimescaleDB + Grafana for trend visualization

---

## 🧭 Course Syllabus (10 Modules)

### **Module 1 — Getting Started**
- Flash “Hello Sensors” sketch to stream IMU (accel/gyro) and mic RMS values.  
- Verify live data in Node-RED Dashboard.  
- Experiment: Tap and observe signal peaks.

### **Module 2 — Mounting & Sampling**
- Rigid vs soft mounting; sensor axis orientation.  
- Sample-rate selection and aliasing basics.  
- Lab: Compare handheld vs mounted readings on a fan.

### **Module 3 — Spectral Analysis (FFT & PSD)**
- Compute FFT and power spectral density in Python.  
- Identify dominant frequency, harmonics, and running speed.  
- Lab: Detect imbalance frequency from PSD plots.

### **Module 4 — Order Analysis & RPM Estimation**
- Relate spectral peaks to machine speed (1×, 2× orders).  
- Lab: Estimate RPM from IMU data without a tachometer.

### **Module 5 — Microphone Fusion**
- Use on-board mic to capture acoustic patterns.  
- Correlate mic bandpower (hum vs whine) with vibration RMS.  
- Lab: Create a 2D plot (IMU RMS vs Mic bandpower).

### **Module 6 — Time-Domain Features & Health Score**
- Compute RMS, kurtosis, crest factor, peak-to-peak.  
- Define baseline and 3σ alert limits.  
- Lab: Compute simple “health index” in Node-RED.

### **Module 7 — Envelope Detection & Impact Analysis**
- Use Hilbert transform or rectify-lowpass for envelope.  
- Detect periodic impulses simulating bearing defects.  
- Lab: Tap sensor lightly at steady intervals.

### **Module 8 — Real-Time Alerts via MQTT**
- Build Node-RED rules for abnormal patterns.  
- Publish alerts to `/mg24/vibe/alerts`.  
- Lab: Add small imbalance (tape) to a fan and detect alert.

### **Module 9 — Data Logging & Dashboards**
- Store data in CSV / TimescaleDB.  
- Build Grafana panels for RMS, PSD trends, and alert history.  
- Lab: Run 30-min endurance test; examine drift.

### **Module 10 — Mini Project**
- Choose a household machine (fan, blender, vacuum).  
- Collect baseline, induce fault, detect change.  
- Deliverables:  
  - Firmware & Node-RED flow  
  - 5 min dataset + Python analysis notebook  
  - 2-page summary of findings

---

## 🗂 Repository Structure

