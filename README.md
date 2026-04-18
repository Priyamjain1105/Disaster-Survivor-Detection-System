# Disaster Survivor Detection System (DSDS) 🛰️🆘

### **"In the first 72 hours of a disaster, every second is a lifeline. We built the eyes that don't blink."**

---

## 📖 The Story: Inspired by India’s Resilience
This project isn't just about code; it’s about the lessons learned from India’s most challenging hours.

* **Uttarakhand (2013):** The "Himalayan Tsunami" showed us that in rugged terrain, ground teams are often cut off. Aerial sight is the only way in.
* **Jammu & Kashmir (2014):** Urban flooding turned Srinagar into a maze. We realized rescue teams need to see through the "clutter" of submerged cities.
* **Kerala (2018):** Massive scale taught us that manual analysis of drone footage is too slow when millions are displaced.

**The Conflict:** Traditional search-and-rescue is slow, resource-heavy, and dangerous for rescuers. Manual drone monitoring leads to human fatigue and missed survivors.

**The Resolution:** I developed an automated, **Single-Stage CNN** detection system designed to process drone imagery in real-time, pinpointing survivors in seconds—not hours.

---

## 🚀 Key Features & "Tweetable" Essence
> **"DSDS: A YOLOv8-powered 'eye-in-the-sky' that detects survivors in disaster zones at 74 FPS, optimized for edge-deployment on rescue drones."**

* **Real-Time Speed:** Operates at **74 FPS** on modern GPUs, far exceeding the 30 FPS industry standard for live video.
* **Edge Optimized:** I specifically utilized **YOLOv8m** to balance the high precision required for small objects with the lightweight architecture needed to fit inside a drone’s onboard computer.
* **Small Object Mastery:** Trained to detect survivors even at altitudes of **120 meters**, where a human might appear as small as a 10x10 pixel block.

---

## 🛠️ The Tech Stack
* **Model:** YOLOv8m (You Only Look Once v8 - Medium)
* **Framework:** PyTorch 2.0 & Ultralytics
* **Hardware:** NVIDIA RTX 3090 (24 GB VRAM)
* **Dataset:** Aerial Person Detection (APD) Dataset (~2,000+ annotated frames)
* **Augmentation:** Mosaic, scaling, and color jitter to simulate harsh disaster environments.

---

## 📊 Visualizing Success

### **1. Real-Time Detection in Flooded Terrains**
`[Place Image: Page 6 - Top image showing "People 0.80" detections in flood water]`
*The model maintains high confidence even when survivors are partially submerged or surrounded by water clutter.*

### **2. Training Progress & Loss Convergence**
`[Place Training Graphs: Page 9 - Results.png graphs]`
*The smooth convergence of Box and Class loss indicates a robust learning phase, reaching an mAP@0.5 of 0.863.*

### **3. Performance Comparison**
| Model | Precision | FPS (GPU) | Suitability |
| :--- | :--- | :--- | :--- |
| Faster R-CNN | 0.784 | 7 | ❌ Too Slow |
| YOLOv5m | 0.821 | 61 | ✅ Suitable |
| **YOLOv8m (Ours)** | **0.874** | **74** | 🚀 **Optimal** |

---

## 🏗️ The Pipeline
1.  **Capture:** Drone captures live video and streams it to a ground station via an encrypted link.
2.  **Inference:** The YOLOv8m engine processes frames, identifying survivors with bounding boxes, confidence scores, and GPS coordinates.
3.  **Alert:** A real-time alert system flags frames with detected persons and logs locations for rescue teams to generate a survivor heatmap.

---

## 🛑 Limitations & Future Scope
* **Thermal Integration:** Current model is daylight-optimized; I plan to integrate infrared imagery for night operations.
* **Embedded Deployment:** Future work involves model quantization and pruning for onboard hardware like NVIDIA Jetson.

---

## 👤 Developer
* **Priyam Jain** - Computer Science & Engineering, VIT Bhopal

---
*Developed as part of the Computer Vision curriculum for the Winter Semester 2025-26.*
