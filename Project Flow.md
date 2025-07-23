---
## 🧠 *Project Flow – IoT-Based Non-Invasive Glucose Monitoring System*
---

### *1. Sensing Layer (Physiological Sensors)*

This layer consists of *multiple non-invasive sensors* collecting real-time biosignals correlated with glucose levels:

| Sensor Type                  | Parameter                         | Purpose                                                                    |
| ---------------------------- | --------------------------------- | -------------------------------------------------------------------------- |
| ECG electrodes               | Heart rate variability (HRV)      | Blood glucose levels affect HRV.                                           |
| GSR (Galvanic Skin Response) | Skin conductance                  | Reflects sympathetic activity, influenced by glucose fluctuations.         |
| Skin temperature sensor      | Skin temperature                  | Glucose levels can alter peripheral circulation and thermoregulation.      |
| NIR sensor                   | CO₂ levels (proxy via absorption) | Indirect marker related to glucose metabolism.                             |
| Blood pressure sensor        | BP + pulse wave velocity          | Vascular changes due to glucose shifts.                                    |
| Skin color sensor (RGB/IR)   | Skin tone/oxygenation             | Affected by perfusion, which can relate to glucose regulation.             |
| Respiration sensor           | Breath rate                       | Respiratory rate can be glucose-sensitive in certain physiological states. |

🛠 These sensors are connected to an *edge device* (e.g., Raspberry Pi, ESP32, Arduino with ADCs + BLE/WiFi).

---

### *2. Edge Processing Layer (Signal Preprocessing + Feature Extraction)*

* *Denoising* and artifact removal (e.g., bandpass filters for ECG, smoothing for GSR).
* *Feature extraction* per sensor:

  * ECG → RR intervals, SDNN, LF/HF ratio  
  * GSR → SCR peaks, amplitude  
  * Temp → ΔT over time  
  * NIR → wavelength-specific absorption  
  * BP → systolic/diastolic changes  
  * Skin tone → ΔRGB/IR ratios  

* These features are *time-synced and normalized* into a feature vector.

---

### *3. Machine Learning Layer (Glucose Estimation Model)*

* *Model types*: Random Forest, Gradient Boosting, or lightweight Neural Networks.  
* *Input*: Feature vector from multiple sensors.  
* *Output: Predicted **blood glucose level* (mg/dL).  
* *Training*: Requires paired data of biosignal features + actual glucose (from glucometer/CGM).

---

### *4. Communication Layer (IoT Gateway)*

* LoRa and Bluetooth module.

---

### *5. Cloud Layer (Storage + Analytics + Alerts)*

* Stores real-time and historical glucose data.  
* Visual analytics (graphs, trends, risk zones). 
* Trigger alerts if glucose crosses thresholds.
* Optionally retrain/update the model based on real user feedback.

---

### *6. Dashboard / Mobile App*

* User-friendly interface for:

  * Real-time glucose readings  
  * Historical trends and prediction graphs  
  * Warnings for hypo-/hyperglycemia  
  * Upload calibration data manually if needed

---

### *System Highlights*

* ⚙ *Completely non-invasive*: No skin puncture, continuous monitoring possible.  
* 🤖 *Multimodal fusion: Leverages **sensor fusion* for better accuracy.  
* 🧠 *ML-powered*: Adaptively learns user-specific glucose patterns over time.  
* 🌐 *IoT-enabled*: Real-time, connected, and remotely accessible.
