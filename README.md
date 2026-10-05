# Robust Statistics -- Automated Anomaly Detection

## Objective
This project tests how different summary statistics and outlier detection methods hold up when a dataset contains extreme values.

## Methodology
- Loaded the California Housing dataset, which has 20,640 observations.
- Computed two groups of summary statistics: ones that are sensitive to outliers (mean and standard deviation) and ones that resist them (median, trimmed mean, IQR and MAD).
- Implemented Tukey Fences by hand, using the IQR to set upper and lower bounds, and flagged house prices that fell outside them.
- Applied Isolation Forest to detect anomalies across multiple features at once instead of price alone.
- Compared the observations flagged by Tukey Fences with those flagged by Isolation Forest.

## Key Findings
- Tukey Fences and Isolation Forest flagged different observations. Tukey looks at one variable at a time, while Isolation Forest looks at combinations of features, so each method catches outliers the other misses.
