## Overview

This project analyzes NFL player tracking data to understand how **pre-snap movement, spatial control, and player behavior** influence passing play success. Using data from the NFL Big Data Bowl (Week 1: Philadelphia Eagles vs. Detroit Lions), I introduce a **novel zone control metric** based on Voronoi diagrams and apply **predictive modeling** to evaluate passing outcomes at both the frame and play level.

The goal is to demonstrate how advanced tracking data can be translated into **actionable football analytics** through visualization, feature engineering, and statistical modeling.

## Key Questions
* How do pre-snap player movements and spatial positioning affect passing play success?
* Can spatial dominance be quantified using player tracking data?
* Which factors are most predictive of unsuccessful vs. successful passing plays?

## Data
* **Source:** NFL Big Data Bowl (Kaggle)
* **Scope:** Week 1 game (Eagles vs. Lions)
* **Note:** Raw tracking data is not included due to file size and Kaggle terms.

## Methods
### 1. Movement Visualization
* Animated visualizations of player trajectories and pre-snap alignment
* Clustering of player movement into three behavioral profiles:
  * **Stable / minimal movement**
  * **Stationary / alignment-focused**
  * **Dynamic / reactive movement**

### 2. Zone Control Metric (Novel Feature)
* Used **Voronoi diagrams** to partition the field into player-controlled zones
* Introduced a **Zone Control Percentage** to quantify spatial dominance:

$$
\text{Zone Control Percentage} = \frac{100}{1 + \text{Number of Defenders in Zone}}
$$'

* Higher values indicate greater offensive spatial control

### 3. Predictive Modeling
* **Model:** Logistic Regression
* **Features:**
  * Yards to go
  * Time remaining in game
  * Zone control percentage
  * Movement cluster
* **Targets:** Passing play success (binary)

## Results
### Model Performance
* **Frame-level accuracy:** ~69%
* **Play-level accuracy:** ~58%

The model performs strongly in identifying **unsuccessful passing plays**, while successful plays are harder to predict due to limited sample size and feature scope.

### Key Findings
* Distance to first down and game pressure (time remaining) are strong predictors
* Spatial congestion negatively impacts passing outcomes
* Movement behavior provides additional context but requires richer feature expansion

## Limitations & Future Work
* Small sample size (single game)
* Limited feature set
* Future improvements could include:
  * Additional games and seasons
  * Nonlinear models (tree-based methods)
  * Expanded spatial-temporal features

## Tools & Technologies
* **R / RStudio**
* dplyr, purrr
* ggplot, ggalt
* gganimate, gifski
* Voronoi geometry (ggvoronoi2, sf, deldir)

## Why this project matters
This project demonstrates:
* Applied machine learning on real-world tracking data
* Feature engineering grounded in spatial reasoning
* Clear analytical thinking and model evaluation
* Ability to translate complex data into interpretable insights

