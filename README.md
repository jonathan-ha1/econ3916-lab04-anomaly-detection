# Robust Statistics -- Automated Anomaly Detection

## Objective
I wanted to see how well different summary statistics and outlier detection
methods hold up when the data contains extreme or corrupted values.

## Methodology
- I loaded the California Housing dataset (20,640 observations).
- I computed two groups of summary statistics: ones that are sensitive to
  outliers (mean, standard deviation) and ones that resist them (median,
  trimmed mean, IQR, MAD).
- I implemented Tukey Fences by hand, using the IQR to set upper and lower
  bounds, and flagged house prices that fell outside them.
- I applied Isolation Forest to detect anomalies across multiple features
  at once, not just price.
- I compared the observations flagged by Tukey Fences against those flagged
  by Isolation Forest.
- I ran a contamination experiment: I corrupted 5% of the data and
  recomputed the statistics to see which ones changed and by how much.

## Key Findings
- Tukey Fences and Isolation Forest flagged different observations. Tukey
  only looks at one variable at a time, while Isolation Forest looks at
  combinations of features, so each method catches outliers the other misses.
- After 5% contamination, the mean shifted by [YOUR VALUE]%, while the median
  shifted by only [YOUR VALUE]%.
- The outlier-resistant measures (median, trimmed mean, IQR, MAD) stayed
  stable under contamination, while the mean and standard deviation did not.# econ3916-lab04-anomaly-detection
