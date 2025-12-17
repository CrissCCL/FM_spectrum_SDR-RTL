# 📡 📻 FM Spectrum Analysis using RTL-SDR

## Overview

This repository contains a **Python-based tool for analyzing the FM broadcast baseband spectrum** using an **RTL-SDR** receiver.

The code captures raw IQ samples from an FM radio station, performs **FM demodulation**, and analyzes the resulting baseband signal using:
- Power Spectral Density (Welch)
- Single FFT analysis
- Time–frequency spectrogram

The project is intended for **educational, laboratory, and signal processing analysis purposes**, with a focus on understanding the **FM stereo multiplex spectrum**.



## 🧰 Hardware Setup

The measurements were performed using a **low-cost RTL-SDR USB dongle** connected to a standard FM broadcast antenna.

### Device

- **SDR Receiver:** RTL-SDR (RTL2832U compatible)
- **Frequency Band:** FM broadcast band
- **Interface:** USB
- **Antenna:** Wideband FM antenna

The RTL-SDR is used exclusively for **IQ data acquisition**, while all signal processing is performed offline in Python.

<p align="center">
<img src="https://github.com/user-attachments/assets/d929ca5d-2eb0-4496-8d00-b7ccac389ebc" alt="SDR-RTL" width="400">
</p>


## 📂 Contents

- 🧠 **src** → Python code for SDR capture, demodulation, and spectrum analysis  
- 📄 **docs** → Theory notes and references  
- 🖼️ **media** → Device photos and spectrum visualizations  


## 📡 System Description

### Signal Processing Chain

1. IQ capture from RTL-SDR  
2. Frequency shifting to baseband  
3. Low-pass filtering  
4. Amplitude limiting  
5. Resampling  
6. FM demodulation  
7. Spectral analysis  

The processing chain follows a **standard digital FM receiver architecture**, focused on spectrum inspection rather than audio playback.



## 📊 Spectrum Analysis & Results

The following figure shows the **complete FM stereo baseband analysis (0–60 kHz)** after demodulation.

It includes:
- Power Spectral Density (Welch)
- Single FFT spectrum
- Time–frequency spectrogram

<p align="center">
<img src="https://github.com/user-attachments/assets/513f25d7-8ff2-4c3c-b969-ac1f9440533c" alt="Spectrum" width="800">
</p>


### FM Stereo Multiplex Components

The spectrum clearly shows the main FM stereo components:

- **0–15 kHz:** Mono audio (L+R)
- **19 kHz:** Stereo pilot tone
- **23–53 kHz:** Stereo difference signal (L−R)
- **38 kHz:** Stereo subcarrier
- **57 kHz:** RDS subcarrier



## ⚙️ SDR Configuration

Key parameters defined in the code:

- Center frequency: FM broadcast station (e.g. 106.7 MHz)
- RF sample rate: 2.048 MS/s
- Gain: Manual gain control
- Number of captured samples: Configurable

These parameters can be adjusted directly at the beginning of the script.


## 🧪 Requirements

- RTL-SDR compatible device
- Python 3.x
- Required Python packages:
  - `numpy`
  - `scipy`
  - `matplotlib`
  - `pyrtlsdr`



## 🚀 Running the Code

The script can be executed directly from **VS Code** or any Python environment:

```bash
python analisisSDR.py
```

## 📚 References

- GNU Radio – Official Documentation: [GNU Radio](https://www.gnuradio.org/)

- Frequency Modulation (FM) – Wikipedia: [Wikipedia Frequency Modulation](https://en.wikipedia.org/wiki/Frequency_modulation)

- FM stereo – Wikipedia: [FM Stereo](https://en.wikipedia.org/wiki/Fm_stereo)

## 📜 License
MIT License  
