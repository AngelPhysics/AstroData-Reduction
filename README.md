# AstroData Reduction: NGC 6118

![status](https://img.shields.io/badge/status-finished-blue)
![license](https://img.shields.io/badge/license-MIT-green)

This repository contains a comprehensive Python-based workflow for the **reduction and calibration of CCD images** of the spiral galaxy NGC 6118, following standard procedures in optical astronomy. The notebook covers all main steps required to transform raw CCD data into science-ready images and catalogs of detected sources, with a focus on photometric calibration and HII region detection.

---

## 🌌 **Main Objectives**

- Demonstrate the full reduction process of optical CCD images from a ground-based observatory.
- Automate and document the construction of calibration frames (bias, flat), cosmic ray removal, bad pixel correction, and background subtraction.
- Produce combined (science) images for different filters (Hα and R).
- Perform photometry and flux calibration for detected stars.
- Detect and characterize HII regions across the galaxy image.

---

## 📚 **Workflow & Key Steps**

1. **Raw Data Organization and Inspection**
   - Automatic discovery and classification of all FITS files into bias, flat, and science images.
   - Extraction and logging of header metadata (OBJECT, EXPTIME, FILTER, etc).

2. **Statistics of Raw Frames**
   - Calculation of mean, median, standard deviation, and extrema for all images.
   - Function definition for reusable image statistics.

3. **SuperBias Creation**
   - Median combination of selected bias frames after outlier rejection to generate a robust master bias.
   - Visualization and quality control of the superbias frame.

4. **SuperFlat Creation**
   - Separate processing for R and Hα flat fields.
   - Subtraction of master bias, central region selection, normalization, and median stacking to produce master flats for each filter.
   - Visualization of superflats for quality assurance.

5. **Cosmic Ray Removal**
   - Application of the `lacosmic` algorithm to science frames to remove cosmic ray artifacts.
   - Batch processing and visual checks.

6. **Science Image Calibration**
   - Subtraction of the superbias and division by the corresponding superflat for each science frame.
   - Output of clean, calibrated images for each filter.

7. **Background Subtraction**
   - Creation and application of background masks to each science frame.
   - Visualization of background models and residuals.

8. **Bad Pixel Detection and Correction**
   - Manual and automatic correction routines for bad pixels/columns.
   - Functions for systematic bad pixel replacement.

9. **Exposure Time Normalization**
   - Scaling of science images to a common exposure time for stacking and comparison.

10. **Combination of Science Frames**
    - Median combination of calibrated, cosmic ray cleaned, exposure-normalized images to generate final “super” images in Hα and R bands.

11. **Detection, Photometry, and Flux Calibration of Stars**
    - Automatic source detection (DAOStarFinder).
    - Aperture photometry on detected stars.
    - Flux calibration using known standard stars, where available.

12. **HII Region Analysis**
    - Creation of “superGalaxy” (deep stack).
    - Galaxy orientation correction and resizing.
    - Detection and cataloging of HII regions (star-forming knots).
    - Visualization with 2D and 3D interactive bubble charts (Plotly).

13. **Final Plots and Conclusions**
    - Summary plots, region catalogs, and scientific discussion.
    - Automated saving of key results and figures.

---

## 🧰 **Libraries & Dependencies**

- `astropy` (io.fits, stats, modeling, visualization)
- `numpy`
- `matplotlib`
- `scipy`
- `photutils`
- `lacosmic`
- `pandas`
- `plotly`
- `glob`

Install all dependencies with:
```bash
pip install astropy numpy matplotlib scipy photutils lacosmic pandas plotly
