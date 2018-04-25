---
layout:     post
title:      "Feature Engineering"
subtitle:   "Data Mining Approach"
date:       2018-4-26 00:39:00
author:     "Snow"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
- Research
---

## Feature Engineering - Data Mining Approach

#### About Paper

[Detecting Click Fraud in Online Advertising - A Data Mining Approach]( http://www.jmlr.org/papers/volume15/oentaryo14a/oentaryo14a.pdf).

- **A Data Mining Approach**.
- Ad Fraud Detection based on click.
- Fraud Detection in Mobile Advertising (FDMA) 2012 Competition.
- **Keywords**: ensemble learning, feature engineering, fraud detection, imbalanced classification

#### Dataset

[==> Download the Database](https://docs.google.com/file/d/0B77LA4oEl-AQTGRHSVNMczJhVTg/edit)

- Publisher Database

  ![1](https://raw.githubusercontent.com/RMSnow/RTB/master/resources/FDMA2012/1.png)

  Eg:

  ![1](https://raw.githubusercontent.com/RMSnow/RTB/master/resources/FDMA2012/3.png)

- Click Database

  ![1](https://raw.githubusercontent.com/RMSnow/RTB/master/resources/FDMA2012/2.png)

  Eg:

  ![1](https://raw.githubusercontent.com/RMSnow/RTB/master/resources/FDMA2012/4.png)

#### First Winner's Entry

- Feature Extraction: [A completint list - 118 predictive features](https://github.com/RMSnow/RTB/blob/master/resources/FDMA2012/1st-feature-list.txt).
  - Three types
    - Click Behavior (#67)
    - Repetitive Click Behavior (#40)
    - High-risk Click Behavior (#11)
  - Statistical Attributes
    - Average
    - Standard Deviation
    - Percentages
  - Correlations
  - Relative Influence

- Discussion

  - Spatial Patterns: **High-Risk Countries Percent**

    > Fraudulent clicks tend to come from some countries (or finer-grained spatial regions) more than others, for example, businesses in India and Indonesia are hardest hit by fraud (Kroll Advisory Solutions, 2012). Most clicks on mobile advertisements also come from these two countries. We tested the top five, ten, fifteen, twenty, and twenty-five high-risk countries (out of two hundred over countries), and found that the top ten high-risk countries works best. For example, usercountry in percent and usercountry id percent are the percentages of invalid clicks originating from India and Indonesia respectively. The large numbers of invalid clicks coming from usercountry sg percent or Singapore could be due to BuzzCity’s penetration tests being conducted from there.

  - Temporal Patterns: **Fined-Grained Time Interbals**

    > For our top click behavior and duplication features, we created conditional features based on finer-grained time intervals to better capture temporal dynamics of click fraud behavior. We divided a day into four six-hour periods: night (12am to 5:59am), morning (6am to 11:59am), afternoon (12pm to 5:59pm), and evening (6pm to 11:59pm). For example, night referredurl percent is the number of distinct referredurls at night divided by the total number of distinct referredurls, and night avg spiky referredurl is the average number of the same referredurl being duplicated within one minute at night. Also, we divided an hour into four fifteen-minute periods: first (0-14), second (15-29), third (30-44), and last (45-59). For example, second 15 minute percent is the number of clicks between 15th to 29th minute divided by total number of clicks.

#### Second Winner's Entry

- Feature Extraction: [A completint list - 41 predictive features](https://github.com/RMSnow/RTB/blob/master/resources/FDMA2012/2nd-FDMA12_TeamMasdar_AppendixA.pdf).
  - Clicktime: **Time Intervals**
  - Statistical Attributes
    - Maximum
    - Average
    - Skewness
    - Variance

#### Third Winners's Entry

- Statistical Attributes: **Unique count**

#### Runner-up's Entry

- Statistical Attributes: **Frequency**

#### Organizer's Entry

- Preprocess: Group by the publisher's status

  ![1](https://raw.githubusercontent.com/RMSnow/RTB/master/resources/FDMA2012/5.png)

- Feature Extraction

  - Statistical Attributes
    - **Ratio / Conversion Rate**
    - nonzero count
    - sum
    - sum of square

- Normalized the feature values to be within `[0, 1]`.

- Model: **Extremely randomized trees (Extra tree)**

#### Conclusions

- Exploratory Data Analysis(EDA): 

  - **Plot**
  - Group by some info (eg: `status`)

- Features Engineering

  - Types

    Spatial, Temporal, User's, Historical, Contextual.

  - Numerical Feature

    - median, mean, mode, min, max, std, var, percent, skewness, absolute, entropy
    - unique count, nonzero count, sum
    - frequency
    - ratio

  - Correlation & Combination

- [【持续更新】机器学习特征工程实用技巧大全](https://zhuanlan.zhihu.com/p/26444240).

#### Resources

- [【持续更新】机器学习特征工程实用技巧大全](https://zhuanlan.zhihu.com/p/26444240).
- [使用sklearn做单机特征工程](http://www.cnblogs.com/jasonfreak/p/5448385.html).
- [机器学习之特征工程](http://www.csuldw.com/2015/10/24/2015-10-24%20feature%20engineering/).