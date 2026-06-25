# 🔥 FireFormer: Multimodal Fire Intelligence Framework

This repository supports the research paper titled:  
**A Multimodal Fire Detection Framework With Uncertainty-Aware
Evidential Fusion and Compact Sensor Synopsis"**  
.

---

## 📦 Overview

This project introduces a real-time, multimodal fire detection and decision-making system that integrates:

- * `FireSentryV3`: A CNN-based visual fire classification model trained on 15 diverse fire-related image classes to extract spatial fire features and estimate visual fire probability.

* `FireSync`: A cross-modal temporal alignment module that compensates for response delays between visual and physical sensor streams before fusion.

* `FireFormer`: A Transformer-based temporal modeling module that processes multivariate time-series data from gas, smoke, flame, infrared, and temperature sensors.

* `TrustNet`: An adaptive sensor reliability estimation module that assigns time-varying trust scores to physical sensors based on disagreement, sensor history, and contextual uncertainty cues.

* `DST Fusion`: An uncertainty-aware decision module that combines visual evidence, temporal evidence, and calibrated sensor likelihoods using Dempster–Shafer Theory.

* `Synopsis Generation`: A compact event-level summarization module that compresses meaningful fire-event data for post-analysis, auditability, and storage optimization.


---

## 🔧 Experimental Setup

<p align="center">
  <img src="control envi.png" width="550"/>
</p>

The data was collected using a custom-made aluminum foil–lined fire container. Sensor data was recorded over **11 days** under both **fire** and **non-fire** conditions.

- **Devices Used**:
  - 2 Raspberry Pi 5 boards for sensor data acquisition
  - 1 Raspberry Pi for camera module & API transmission


---

## 🔍 Internal Monitoring Snapshot

The container interior was monitored using a camera. The image below shows the internal view during both **fire** and **non-fire** conditions, demonstrating how the system captured CNN predictions:

<p align="center">
  <img src="inside_view.PNG" width="600"/>
</p>

---
👉 [**Internel view video**](https://drive.google.com/file/d/1R-KatON6-M9cfiwIRvz1avl7cfYP3kun/view?usp=drive_link)


## 📊 Fire Event Sensor Plot

This figure visualizes how sensor values behave during a fire event. The CNN fire label is shown as a dashed black line. The spike patterns indicate changes in gas, smoke, IR, and temperature:

<p align="center">
  <img src="sen.PNG" width="1000"/>
</p>

---

## 📷 FireSentryV3 (Fire Image Classification API)

FireSentryV3 is trained on a **15-class image dataset**, covering 14 real-world fire scenarios and 1 non-fire category.  
The API allows image upload or test image selection.

<p align="center">
  <img src="FiresentryV3.PNG" width="700"/>
</p>

**Prediction Output:**

<p align="center">
  <img src="pre.PNG" width="450"/>
</p>

---

## 🌡️ FireFormer + DST Decision API

The second API allows users to input live sensor data and receive a combined CNN + Transformer + DST-based fire status.

You can either:
- 🔄 **Link your real-time sensor setup** to the API for continuous decision-making, or
- 📤 **Upload your own sensor dataset** in `.csv` format to simulate and test fire predictions.
  
<p align="center">
  <img src="Main_dst.PNG" width="420"/>
</p>

**Fire Decision Result (Fire):**

<p align="center">
  <img src="fire_dst.PNG" width="450"/>
</p>

**Fire Decision Result (No Fire):**

<p align="center">
  <img src="nofire_dst.PNG" width="450"/>
</p>

---

## 📹 Demonstration Videos

The following videos demonstrate API functionality:

- 🔍 **Fire Image Classification (FireSentryV3)**  
- 🔁 **Sensor Fusion and DST Fire Decision (FireFormer + DST)**  
- 🎥 **Internal Camera Feed Showing Fire On/Off Conditions**

👉 [**Watch API Working Video**](https://drive.google.com/file/d/1VTaWr-ia6uK9t6HoaYrKlwDpoUcaVdWH/view?usp=drive_link)  
👉 [**Sensor Dataset**](https://drive.google.com/file/d/17oPw8458RQolE-f0YxzGmV3YmXW7XbDi/view?usp=drive_link)

---

## 🧪 Data Collection Process

- **Sensors Used**: Smoke, Flame, Temperature, Infrared, Custom Memristor-Based Gas Sensor
- **Sample Rate**: 11 continuous days
- **Export Format**: CSV logs per session with timestamp, raw sensor values, and CNN prediction labels

---

## 🔐 Note

The codebase for model training and API deployment is currently under private review. Only demo videos and sample data logs are shared. Final code will be released upon acceptance.

---

## 💡 Citation

Please cite our work if you find this useful (citation format will be updated post-publication).
