# AstroData Reduction: NGC 6118

![status](https://img.shields.io/badge/status-in--progress-blue)
![license](https://img.shields.io/badge/license-MIT-green)

This repository contains a complete astronomical data reduction workflow applied to CCD images of the spiral galaxy **NGC 6118**, observed with the **Jacobus Kapteyn Telescope (JKT)**. The process is implemented in **Python using JupyterLab**, and documented with **Sphinx**.

---

## 🔭 Project Overview

This project performs the full preprocessing and scientific analysis of CCD data, including:

- **SuperBias** creation from multiple bias frames
- **SuperFlat** generation using twilight flats (R and Hα filters)
- **Cosmic ray removal** (L.A.Cosmic)
- **Bad pixel correction** (manual + automated)
- **Background subtraction**
- **Temporal normalization**
- **Image composition** in R and Hα bands
- **Aperture photometry** of stars
- **Detection and analysis of HII regions**
  - Interactive 2D and 3D bubble charts with Plotly

