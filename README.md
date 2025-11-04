#AIPI 510 Module Project 2 – Random Number Generator Statistical Analysis
Overview

This project investigates whether different random number generators (RNGs) in Python—random, numpy.random, and secrets—produce statistically equivalent uniform distributions.
We generate random samples from each RNG and apply several statistical tests to evaluate uniformity and similarity between their outputs.

Experimental Design

RNGs tested:

random.random()

numpy.random.random()

secrets.SystemRandom().random()

Sample size: 1,000 random values per RNG

Values divided into 10 equal bins across [0, 1)

Expected count: 100 values per bin if perfectly uniform

Statistical Tests
Test	Purpose	Result
Chi-Square Goodness-of-Fit	Tests if each RNG’s output follows a uniform distribution	All p > 0.05
Chi-Square Test of Independence	Tests if distributions differ across RNG types	p = 0.19
Kolmogorov–Smirnov (KS) Test	Compares continuous distributions between RNGs	All p > 0.1

Effect sizes (Cohen’s w) were around 0.1 or smaller, indicating minimal practical differences.

Power Analysis

A post-hoc power analysis confirmed that the sample size provided moderate power to detect small deviations:

Power = 0.56 for small deviations (w = 0.1)

Power = 0.15 for very small deviations (w = 0.05)

Running the Code

All analysis is contained in the script data_and_stats_modeling_code.py.
To run the project:

python data_and_stats_modeling_code.py


This script will:

Generate 1,000 random values from each RNG.

Perform the chi-square and KS tests.

Output test statistics, p-values, and power analysis results.

Conclusion

All three RNGs—Python’s random, NumPy’s random, and secrets—produce statistically equivalent, uniformly distributed outputs for 1,000 samples.
No evidence of bias or systematic deviation was found in any test.
