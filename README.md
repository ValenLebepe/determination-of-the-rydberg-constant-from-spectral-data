# Determination of the Rydberg Constant from Spectral Data

A Python-based physics data analysis project that determines the Rydberg constant by analyzing the hydrogen Balmer series. The project demonstrates advanced fitting techniques like **weighted linear regression** on linearized spectral data, full **error propagation**, and professional **visualization** with Matplotlib and Plotly.

 **Key Libraries:** `NumPy`, `SciPy` (for `curve_fit` and optimization), `Matplotlib`, `Plotly`, `pandas`

## 🎯 Project Overview

The goal of this project was to experimentally determine the fundamental Rydberg constant ($R_H$) by:
1.  Measuring the wavelengths of the hydrogen Balmer lines (H-α, H-β, H-γ, H-δ) using a spectrometer.
2.  Applying **Gaussian fits** to the spectral peaks to precisely determine their central wavelengths and uncertainties.
3.  **Linearizing the Rydberg formula** and performing a weighted linear least-squares regression to extract $R_H$ from the slope.
4.  Propagating all measurement uncertainties to obtain a final uncertainty for the calculated constant.

## 📊 Key Result

The experimental value for the Rydberg constant was determined to be:

**$R_H$ = (10975956.87 ± 125.91) m⁻¹**

This result was derived from the slope of the best-fit line in the linearized Rydberg relation, achieving a high level of precision.

![Linearized Rydberg Plot](https://github.com/ValenLebepe/Determination-of-the-Rydberg-Constant-from-Spectral-Data/blob/main/Results%20Plots/Rydberg%20Formula%20Plot.png)

*Figure 1: The linearized Rydberg plot. The slope of the weighted best-fit line yields the experimental value of* $R_H$.

## ⚙️ How It Works: Analysis Pipeline

The analysis is structured in a clear pipeline within the `Codes` directory:

1.  **Calibration:** A HeNe laser spectrum was used to calibrate the spectrometer and determine a systematic wavelength offset.
2.  **Spectral Peak Fitting:** Gaussian functions were fitted to each Balmer line to accurately find their centers, accounting for instrumental broadening.
                           
![H-Alpha Gaussian Fit](https://github.com/ValenLebepe/Determination-of-the-Rydberg-Constant-from-Spectral-Data/blob/main/Results%20Plots/Ha%20spectrum%20Plot.png)

*Figure 2: Measured spectrum of the H-α line with Gaussian fit.*

3.  **Linear Regression:** The Rydberg formula was linearized into the form $y = R_H \cdot x$, and a **weighted regression** was performed, where each point was weighted.
4.  **Uncertainty Propagation:** Uncertainties from wavelength measurements were propagated through the Gaussian fitting and linear regression processes to determine the final uncertainty in $R_H$.

## 📁 Repository Structure

A high-level overview of the project organization:
```
Determination-of-the-Rydberg-Constant-from-Spectral-Data/
│
├── Data/
│   └── Raw and processed data files (.csv) from the experiment.
│       - Hydrogen Balmer series spectra (H-α, H-β, H-γ, H-δ)
│       - HeNe laser calibration data
│       - Background noise measurements
│
├── Codes/
│   └── The core analysis scripts and notebooks.
│       - `rydberg_analysis.py`: The main Python script containing the complete analysis pipeline.
│       - `analysis_clean.ipynb`: A clean Jupyter notebook version of the main script.
│       - `analysis_with_notes.ipynb`: A notebook with the same code but detailed explanations of the physics and code.
│       - *The complete workflow includes: calibration, Gaussian fitting, uncertainty propagation, linear regression, and visualization.*
│
├── Results_Plots/
│   └── Final publication-quality figures (.png) output by the scripts.
│       - Gaussian fits for each spectral line
│       - Plot of the linearized relationship and best-fit line
│       - Overview of the full hydrogen spectrum
│
└── README.md
```


## 🛠️ Technical Implementation

- **Language:** Python
- **Key Libraries:** `NumPy`, `SciPy` (for `curve_fit` and optimization), `Matplotlib`, `Plotly`, `pandas`
- **Core Techniques:** Gaussian curve fitting, weighted least-squares regression, systematic error calibration, uncertainty propagation.

## 🔬 Note on Academic Integrity

This repository contains the **code and data** for the project. The formal lab report, which contains the detailed theoretical background and full discussion, is not published here to uphold my academic institution's integrity policies. The code and results presented here demonstrate the technical implementation and data analysis skills developed in this project.

## 👨‍💻 View the Analysis Code

For insight into the analysis process—including explanations of weighted vs. unweighted fitting, uncertainty propagation, and `scipy.curve_fit` usage, see the notebook with notes:
**[Codes/analysis_with_notes.ipynb](Codes/rydberg_analysis_with_notes.ipynb)**
