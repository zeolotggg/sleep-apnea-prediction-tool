# OSA Risk Prediction Tool

**Version:** v2.0  
**Last updated:** 2026-05-08  
**Associated manuscript:** "Integrating Complete Blood Count Parameters with Demographic 
         Characteristics for Obstructive Sleep Apnea Prediction in 
         Chinese Adults: A Machine Learning Approach"

---

## Overview

A web-based clinical risk prediction tool for obstructive sleep apnea (OSA) based on a logistic regression nomogram. The tool calculates a predicted probability of OSA (defined as AHI ≥ 5 events/hour) using readily available clinical and complete blood count (CBC) parameters.

This tool is intended as a **pre-screening aid** for clinicians evaluating patients referred for sleep assessment. It is **not** a diagnostic instrument and does not replace polysomnography (PSG) or home sleep apnea testing (HSAT).

## Predictors

The model incorporates the following **9 variables**:

| Variable | Unit |
|---|---|
| Gender | Male / Female |
| Age | years |
| BMI | kg/m² |
| Hemoglobin (sex-specific z-score) | g/L (converted internally) |
| Lymphocyte count | ×10⁹/L |
| Red cell distribution width (RDW) | % |
| Mean corpuscular hemoglobin (MCH) | pg |
| Platelet count | ×10⁹/L |
| Mean platelet volume (MPV) | fL |

> **Note:** Hemoglobin is entered as a raw value (g/L) and internally converted to a sex-specific z-score using training cohort parameters (Male: mean = 152.66, SD = 5.7; Female: mean = 136.20, SD = 5.0).

## Model Lock Statement

The regression coefficients and nomogram scoring system implemented in this tool correspond **exactly** to the final logistic regression model reported in the associated manuscript. **No modifications** to model parameters, variable weights, or prediction formula will be made to this version (v2.0). Any future changes to the model would be released as a new version with a separate changelog entry.

## How to Use

1. Download or open `OSA_Risk_Prediction_Tool_v2.html` in any modern web browser.
2. Enter patient clinical and CBC values in the input fields.
3. Click **Calculate** to obtain the predicted OSA probability and risk category.
4. All computations run locally in the browser — **no data is transmitted to any server**.

## Development Cohort

- **Study design:** Single-center retrospective cohort with **temporal validation**
- **Sample size:** n = 5,828
    - **Training cohort (n = 4,330):** patients enrolled January 2018 – December 2022; 
      used for feature selection, model development, and hyperparameter tuning
    - **Validation cohort (n = 1,498):** patients enrolled January 2023 – March 2024; 
      held out entirely from model development and used only for final performance 
      assessment on temporally distinct data
- **Population:** Adults referred for suspected OSA at a tertiary sleep center in China
- **OSA prevalence in cohort:** 83.5%
- **Outcome:** AHI ≥ 5 events/hour (binary classification)

## Version History

| Version | Date | Description |
|---|---|---|
| v2.0 | 2026-05-08 | Updated interface to align with manuscript Figure 7; improved layout, Hb z-score display, and risk stratification panel |
| v1.0 | 2025-12-15 | Initial release |

## License

This tool is provided for academic and clinical research purposes. Please cite the associated manuscript if you use or adapt this tool.

## Contact

For questions or issues, please open an [Issue](../../issues) in this repository.
