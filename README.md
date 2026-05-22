# AuraScope by AuraAudio 🌊🎤

**Live Low-Frequency, LFN, and Structural Resonance Analyzer**

AuraScope is a lightweight, purely browser-based (Single Page App) acoustic measurement tool designed to analyze live microphone inputs. Built by **AuraAudio**, this tool bypasses standard browser audio processing to capture raw acoustic data, making it an excellent preliminary testing rig using standard laptops or professional external measurement microphones like the **miniDSP UMIK-1**.

## 📊 Overview (v2.2)

Standard audio visualizers are built for music, artificially rolling off sub-bass frequencies. AuraScope is engineered specifically for environmental acoustic analysis. 

With **v2.2**, AuraScope doesn't just measure Low Frequency Noise (LFN), it now measures the **Mid-Frequency** (Speech Band) and **Broadband** levels to give you context on whether a nuisance noise is being "masked" by background noise or if it is piercingly perceivable. It also introduces a real-time **Severity Assessment Engine** to immediately classify readings.

## ✨ Features

*   **Zero-Install SPA:** Runs entirely from a single `index.html` file. No dependencies, no npm, no backend required.
*   **Raw Audio Pipeline:** Disables WebRTC filters (AGC, Noise Suppression) to ensure the signal is acoustic truth.
*   **Plug-and-Play Measurement Mics:** Automatically detects and switches to external USB measurement microphones.
*   **Six-Metric Analysis Engine:**
    *   **Vibration Proxy:** < 20 Hz (Infrasound / Structural Rumble)
    *   **LFN:** 20 Hz – 100 Hz (Low Frequency Noise)
    *   **LF:** 100 Hz – 250 Hz (Low Frequency)
    *   **Mid-Frequency:** 250 Hz – 2 kHz (Background / Masking Noise)
    *   **Broadband:** 10 Hz – 20 kHz (Total Acoustic Energy)
    *   **Peak Resonance:** Exact Hz standing wave / room mode detection.
*   **Severity Assessment Badges:** Live grading from *Low* to *Extreme* based on dBFS limits.
*   **Long-Term Logging:** Aggregates running averages (1 Min, 1 Hour, 24 Hours, 1 Month) instantly without freezing the browser.
*   **CSV Exports:** Memory-chunked CSV builder allowing millions of rows of data export for use in Excel/MATLAB.
*   **Light & Dark Mode:** Accessible themes with a unified UI. (Light mode default).

## 🚀 Usage

1. Clone this repository or download `index.html`.
2. Open `index.html` in any modern web browser (Chrome, Edge, Firefox).
    * *Note: Browsers require microphone access to be served over a secure context (`https://`) or `localhost`.*
3. Click **Start Measurement** and grant microphone permissions.
4. Leave it running to populate the Historical Lookback table.
5. Click **Download CSV** before closing to save your session.

## 🛣️ Roadmap

- [x] Contextual Mid-Band & Broadband tracking
- [x] Millisecond Data Logging & CSV Exports
- [ ] **Phase 2: Calibration & Accuracy**
  - Microphone Calibration File parser (Upload `.txt` files for UMIK-1 flat response correction).
  - A-weighting, C-weighting, and Z-weighting toggles.
- [ ] **Phase 3: Temporal Data**
  - Real-time Spectrogram / Waterfall plot for identifying lingering resonances (RT60 decay estimation).

## 📄 License
MIT License - Copyright (c) 2026 AuraAudio
