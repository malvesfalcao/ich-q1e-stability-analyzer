# ich-q1e-stability-analyzer
ICH Q1E Stability Analyzer


## Why I Built This

In pharmaceutical development, stability data is the ultimate source of truth. However, evaluating that data often means wrestling with fragile Excel spreadsheets or navigating clunky, expensive commercial Quality Management Systems (QMS). 

After years of managing large-scale stability programs—overseeing more than 1,500 concurrent studies and leading complex Out of Specification (OOS) investigations—I wanted a better way. I built this open-source Python utility to give bench scientists, Analytical R&D teams, and QA professionals a lightweight, mathematically rigorous tool to evaluate degradation profiles without the friction.

Whether you are projecting shelf-life for an IND submission or investigating a suspicious 12-month assay pull, this tool is designed to provide immediate, compliant, and visual answers.

---

## What It Actually Does

Instead of just plotting lines on a graph, this tool applies the strict statistical principles outlined in **ICH Q1E** and standard industry practices for Out of Trend (OOT) detection:

* **Shelf-Life Projection:** It automatically calculates the one-sided 95% Lower Confidence Bound (LCB) of the mean regression line and finds exactly where it intersects your Lower Specification Limit (LSL).
* **Automated OOT Flagging:** No more guessing if a data point is a true outlier. The script calculates standardized residuals and flags any point falling outside the 95% Prediction Interval. 
* **Interactive & Frictionless:** You don't need to be a software engineer to use it. Run the script, punch in your timepoints and assay values via the command prompt, and get instant visual and tabular results.
* **Publication-Ready Visuals:** Generates clean `matplotlib` graphs highlighting normal data, regression lines, confidence bands, and clearly marked outliers.

---

## The Scientific Rigor Under the Hood

To ensure this tool aligns with pharmaceutical quality standards, the mathematics are intentionally transparent:

* **Extrapolation:** Utilizes the margin of error for the mean prediction to construct the confidence bound.
* **Outlier Detection:** Calculates leverage ($h_i$) to adjust for a timepoint's position relative to the study mean, and computes the standardized residual ($r_i$). Any absolute standardized residual $> 2.0$ is mathematically flagged as an OOT result.

---
