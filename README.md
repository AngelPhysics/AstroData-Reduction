# AstroData Reduction: NGC 6118

![status](https://img.shields.io/badge/status-finished-blue)
![license](https://img.shields.io/badge/license-MIT-green)

Reproducible pipeline in **Python** (JupyterLab) for the **photometric reduction**
of astronomical images — using the galaxy *NGC 6118* as a case study — integrating
all classic calibration stages:

1. **SuperBias** and bias subtraction  
2. Multiband **SuperFlats** (R and H-α) and illumination correction  
3. **Cosmic ray** removal  
4. Temporal and background normalization  
5. Star detection and photometry  
6. Identification and characterization of **H II regions**  
7. Interactive 2-D and 3-D visualizations of the results :contentReference[oaicite:0]{index=0}

Full documentation is generated with **Sphinx** and will be available via GitHub Pages
(under construction).

## 🚀 Quick Setup with pip (alternative)

If you are not using conda, you can recreate the environment using `pip`:

```bash
python3 -m venv envAstro1
source envAstro1/bin/activate
pip install -r requirements.txt


