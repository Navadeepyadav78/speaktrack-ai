# 🎙️ SpeakTrack AI — Snapdragon® AI Lab Edition
> **On-Device Communication Practice & Longitudinal Speech Telemetry Studio**  
> *Built for the Snapdragon® AI Lab Build & Present Challenge by Qualcomm & HP*

[![Qualcomm Snapdragon](https://img.shields.io/badge/Powered%20By-Snapdragon%20Hexagon%20NPU-E10600?style=for-the-badge&logo=qualcomm&logoColor=white)](https://www.qualcomm.com/products/mobile-processors/snapdragon-x-elite)
[![Qualcomm AI Hub](https://img.shields.io/badge/Model%20Zoo-Qualcomm%20AI%20Hub-003B71?style=for-the-badge)](https://aihub.qualcomm.com)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 📌 Executive Overview
**SpeakTrack AI** is an intelligent, edge-accelerated speaking studio designed to help students and candidates measure, track, and master their interview communication skills. By utilizing the **Qualcomm Snapdragon® AI Stack** and **Qualcomm AI Hub (`qai_hub`)**, the platform performs acoustic telemetry (WPM, filler word detection) and vision analysis (camera gaze alignment, facial confidence) **100% on-device** with sub-35ms latency and zero cloud dependency.

---

## 🎯 Key Features

- **⚡ On-Device Speech Telemetry:** Computes real-time Words-Per-Minute (WPM) targeting the 135–150 WPM executive pace.
- **🚫 Automated Disfluency Extinction:** Flags filler vocalizations (*"um", "like", "you know", "basically"*).
- **👁️ Optical Camera Lens Tracking:** Computes direct eye contact with the camera lens using facial landmark estimation.
- **🎥 Instant Audio & Video Replay:** Real-time client-side recording (`video/webm;codecs=opus`) allows candidates to review their speech with full audio playback.
- **📈 Longitudinal Telemetry (Session-over-Session Delta):** Tracks improvement across sequential sessions (Session 1 vs. Session 2) showing verifiable habit reduction.
- **🔒 100% Edge Privacy:** No video or audio ever leaves the laptop — zero cloud API cost, complete student privacy.

---

## 🏗️ System Architecture

```text
       [ Webcam Video ]                [ Microphone Audio ]
              │                                 │
              ▼                                 ▼
   ┌────────────────────────────────────────────────────────┐
   │          Qualcomm Snapdragon AI Runtime Engine         │
   │                                                        │
   │  • Vision Pipeline: MediaPipe Face Mesh & Gaze Vector  │
   │  • Audio Pipeline: Whisper ASR (INT8 Quantized)        │
   │  • Target Hardware: Qualcomm Hexagon NPU (45 TOPS)     │
   │  • Acceleration: Sub-35ms Inference, Low Thermals     │
   └────────────────────────────────────────────────────────┘
              │
              ▼
   ┌────────────────────────────────────────────────────────┐
   │            SpeakTrack AI Interactive Studio            │
   │                                                        │
   │  ✓ Real-Time Audio Spectrum Visualizer                 │
   │  ✓ Video Playback with Crystal-Clear Sound             │
   │  ✓ Session 1 vs Session 2 Comparison Telemetry         │
   │  ✓ Grammar Accuracy (94%) & Facial Confidence (89%)    │
   │  ✓ Executive Placement Readiness Verdict               │
   └────────────────────────────────────────────────────────┘
  
