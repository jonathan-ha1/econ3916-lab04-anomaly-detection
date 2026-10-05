# Robust Statistics -- Automated Anomaly Detection

## Objective
Compare outlier-resistant and standard summary statistics on housing price data, then test two methods for finding unusual observations.

## Methodology
- Loaded the California Housing dataset (20,640 observations).
- Computed six summary statistics on house prices: mean, median, trimmed mean, standard deviation, interquartile range (IQR), and median absolute deviation (MAD).
- Grouped these into measures that are sensitive to extreme values (mean, standard deviation) and measures that resist them (median, trimmed mean, IQR, MAD).
- Built Tukey Fences by hand, using the quartiles and IQR to set upper and lower cutoffs, and flagged any price outside those fences as an outlier.
- Applied Isolation Forest to look for anomalies across multiple features at once, not just price.
- Compared the observations flagged by each method to see where they agreed and where they differed.
- Ran a contamination experiment, corrupting 5% of the data and recalculating each statistic to see which ones changed.

## Key Findings
- Tukey Fences and Isolation Forest flagged different observations. Tukey only looks at one variable (price), while Isolation Forest considers combinations of features, so a house can look normal on price alone but unusual overall, or the reverse.
- After corrupting 5% of the data, the median, trimmed mean, IQR, and MAD held steady, while the mean and standard deviation did not.
- The better method depends on the question: Tukey is simple and easy to explain for a single variable, while Isolation Forest catches unusual patterns that a one-variable rule misses.
