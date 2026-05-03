Automated Media Processing Pipeline (Headless Engine)
[PROPRIETARY SYSTEM]  
Note: The source code for this project is private to protect proprietary automation logic and commercial API integrations. Functional demonstrations are available upon request during technical interviews.

Project Overview
This is a high-performance, zero-GUI (headless) video synthesis engine developed in Python. It leverages the Blender Python API (bpy) to automate the entire post-production workflow—from raw media ingestion to final render—without any manual human intervention.

The system is designed for rapid batch processing, transforming disparate data sources (audio, text, and 3D scenes) into synchronized, high-retention video content.

Technical Stack
Core Orchestration: Python 3.11+

Graphics Engine: Blender API (Headless Rendering)

Data Integration: JSON parsing for frame-accurate event triggers

Audio Processing: API-driven TTS with automated silence trimming

Security: Environment-based API key isolation (Dotenv architecture)


Architectural Highlights
1. Agnostic Input Scaling (Universal Crop)
The engine implements a mathematical scaling algorithm that eliminates the need for manual cropping. By calculating the ratio between source dimensions and the target 9:16 (1440x2560) canvas, it executes a perfect center-crop.

Logic: max(scale_w, scale_h) ensures the viewport is always filled, regardless of the input being 16:9, 4:3, or 1:1.

2. Frame-Sync Event Triggers
The pipeline parses timestamped JSON data to synchronize visual modifications (Color Grading shifts, Motion Blur, and Glitch FX) with specific audio cues. This ensures that visual "impacts" occur precisely on the target frame.

3. Mathematical Seamless Looping
To ensure infinite playback retention, the system calculates the exact duration of the audio stream and applies a Surgical Trim of 0.15s (calibrated to FPS) at the start and end of the sequence. This removes "dead air" and creates a perfect audio-visual loop.

4. CLI-Driven Pipeline
The entire process is triggered via a single command, allowing the engine to run on remote servers or local machines without a monitor, significantly reducing hardware overhead.


Performance & Scalability
Automation Level: 100% (Zero manual clicks)

Input Variability: High (Supports all major MP4/MOV/AVI formats)

Deployment: Structured for easy integration with MySQL for batch-render logging and performance analytics.
