# AuraScope by AuraAudio 🌊🎤

**Live Low-Frequency, LFN, and Structural Resonance Analyzer**

AuraScope is a lightweight, purely browser-based (Single Page App) acoustic measurement tool designed to analyze live microphone inputs for Low Frequency (LF), Low Frequency Noise (LFN), Air/Structure-Borne Vibration, and Peak Resonance.

Built by **AuraAudio**, this tool bypasses standard browser audio processing to capture raw acoustic data, making it compatible with built-in device microphones as well as professional external measurement microphones like the **miniDSP UMIK-1**.

## 📊 Overview

Standard audio visualizers are built for music and speech, artificially rolling off sub-bass frequencies and squishing low frequencies into a few pixels. AuraScope is engineered specifically for acoustic measurement and environmental noise analysis. 

By leveraging a massive FFT size (32,768 bins) and forcing the browser to disable automatic gain control (AGC), echo cancellation, and noise suppression, AuraScope acts as a surprisingly accurate preliminary measurement tool right from your browser.

## ✨ Features

*   **Raw Audio Pipeline:** Disables WebRTC filters (AGC, Noise Suppression) to ensure the signal is acoustic truth, not a processed vocal mix.
*   **Plug-and-Play Measurement Mics:** Automatically detects and switches to external USB measurement microphones (e.g., miniDSP UMIK-1, Dayton Audio UMM-6).
*   **High-Resolution Low-End FFT:** Uses an FFT size of 32,768 samples (~1.46 Hz resolution at 48kHz) to detect exact room modes and structural resonances.
*   **Logarithmic dBFS Band Averaging:** Calculates true acoustic energy over specific critical bands:
    *   **Vibration Proxy:** < 20 Hz (Infrasound / Structural Rumble)
    *   **LFN:** 20 Hz – 100 Hz (Low Frequency Noise)
    *   **LF:** 100 Hz – 250 Hz (Low Frequency)
*   **Peak Resonance Detection:** Automatically scans the 10Hz–500Hz range to highlight the most prominent resonant frequency in real-time.
*   **Logarithmic Spectrum Graph:** Custom-built HTML5 Canvas graph prioritizing the low-frequency spectrum for readability.

## 🚀 Usage

No build step or server is required. 
1. Clone this repository or download `index.html`.
2. Open `index.html` in any modern web browser (Chrome, Edge, Firefox).
    * *Note: Browsers require microphone access to be served over a secure context (`https://`) or `localhost`.*
3. Click **Start Measurement** and grant microphone permissions.
4. Select your preferred microphone from the dropdown.

## 🛣️ Roadmap

We are constantly improving AuraScope to make it the premier web-based acoustic measurement tool.

- [ ] **Phase 1: Calibration & Accuracy**
  - Microphone Calibration File parser (Upload `.txt` files for UMIK-1 flat response correction).
  - A-weighting, C-weighting, and Z-weighting (flat) toggle switches.
- [ ] **Phase 2: Temporal Data**
  - Real-time Spectrogram / Waterfall plot for identifying lingering resonances (RT60 decay estimation).
  - Time-series logging of LFN limits over a set duration.
- [ ] **Phase 3: Export & Portability**
  - Export session data to `.csv` for use in Excel or external plotting tools.
  - Progressive Web App (PWA) integration for native-like offline installation on iOS/Android.

## 📄 License
MIT License - Copyright (c) 2026 AuraAudio
