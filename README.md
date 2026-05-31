# Marketing Campaign Experimentation Analysis

This project analyzes a marketing A/B test to understand whether showing users advertisements helped increase conversions compared to a control group.

The goal was not just to calculate conversion rates, but to answer a practical business question:

**Should this campaign be scaled, paused, or tested further?**

## Project Overview

In this analysis, I used a public marketing A/B testing dataset where users were split into two groups:

* **Ad group:** users who were exposed to advertisements
* **Control group:** users who were shown a PSA/control message

The main outcome was whether a user converted or not.

I compared both groups, measured the conversion lift, tested whether the difference was statistically significant, and translated the results into a business recommendation.

## What I Did

I started by downloading and cleaning the dataset, then checked for missing values, duplicate users, and correct experiment group labels.

After that, I calculated the main experiment metrics:

* Number of users in each group
* Number of conversions
* Conversion rate
* Absolute conversion lift
* Relative conversion lift

To make sure the results were not just random noise, I used a two-proportion z-test to compare conversion rates between the ad group and the control group.

I also calculated confidence intervals to understand the uncertainty around the conversion rates and used bootstrap sampling to estimate the likely range of campaign lift.

Finally, I used logistic regression to check whether being in the ad group was still associated with higher conversion after accounting for ad exposure, day, and hour.

## Methods Used

* Data cleaning and validation
* A/B testing
* Conversion rate analysis
* Absolute and relative lift calculation
* Two-proportion z-test
* Confidence intervals
* Bootstrap sampling
* Logistic regression
* Segment analysis by day and hour
* Business recommendation

## Tools Used

* Python
* pandas
* NumPy
* SciPy
* statsmodels
* matplotlib
* kagglehub

## Dataset

The dataset used in this project is the public **Marketing A/B Testing** dataset from Kaggle.

It contains user-level experiment data, including:

* User ID
* Test group
* Conversion outcome
* Total ads seen
* Day with the most ad exposure
* Hour with the most ad exposure

## Key Business Question

The main question this project answers is:

**Did the advertising campaign lead to a meaningful increase in conversions compared to the control group?**

To answer this, I looked at both the size of the lift and whether the result was statistically significant.

## Project Output

The analysis produces several outputs:

* Overall experiment summary
* Conversion lift by group
* Confidence intervals for conversion rates
* Bootstrap confidence interval for campaign lift
* Logistic regression results
* Segment-level lift by day and hour
* Final business recommendation

The saved output files include:

```text
experiment_summary.csv
conversion_lift_by_day.csv
conversion_lift_by_hour.csv
ab_test_results.csv
```

## Why This Project Matters

Marketing teams often need to decide whether a campaign is worth scaling. Looking only at raw conversion rates can be misleading because a small difference may happen by chance.

This project shows how experimentation can support better decisions by combining business metrics with statistical testing.

Instead of simply saying the ad group performed better or worse, the analysis checks whether the difference is meaningful enough to support a rollout decision.

## Final Recommendation Logic

The ad campaign improved conversion. The ad group converted at 2.55%, compared with 1.79% for the control group. This equals an absolute lift of 0.77% and a relative lift of 43.09%. The result is statistically significant, so the campaign can be scaled further. However, the team should continue monitoring cost per conversion and performance across days and hours.


