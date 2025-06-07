# Anime Performance Analysis — STA 160 Final Project
This repository contains the full R code and supporting materials for my final project in STA 160. The project explores how various production factors (e.g., release season, studio, genre, source material) influence the success of anime titles using data-driven statistical techniques and visualizations.
---
## Project Overview
Title: Report on the Analysis of Anime Performance by Production Factors

### Goal:
To understand which production-related features are most closely correlated to an anime's success, measured through metrics such as score, rank, popularity, and member count. This is done using exploratory data analysis (EDA), principal component analysis (PCA), multiple correspondence analysis (MCA), clustering (k-means), and regression modeling.

### Dataset:
Anime Dataset 2023 from Kaggle (originally scraped from MyAnimeList API). The dataset includes metadata on 20,000+ anime titles with variables such as:
- Title, release season, studio, producers
- Genres, type, source material
- Popularity, rank, user score, number of members/favorites
---
## Methods Used
- Data Cleaning and Transformation
  - Column standardization, factor lumping, handling missing values
  - Feature engineering for episode duration, age ratings, etc.
  - Univariate and Bivariate EDA
  - ggplot2, skimr, DataExplorer
  - Density plots, boxplots, bar charts, correlation heatmaps
- Multivariate Analysis
  - PCA on numeric performance features (e.g., score, rank, popularity)
  - MCA on categorical features (e.g., genre, studio, source)
  - K-means clustering on combined PCA/MCA space
- Modeling
  - Linear regression predicting anime score
  - Cluster-robust standard errors using sandwich and lmtest packages
  - Feature importance via coefficient significance
---
## Dependencies
This project was built in R (version 4.5.0) and uses the following libraries:
```r
library(tidyverse)
library(janitor)
library(skimr)
library(DataExplorer)
library(ggrepel)
library(corrplot)
library(car)
library(multcomp)
library(fastDummies)
library(lmtest)
library(sandwich)
library(knitr)
library(tibble)
library(broom)
library(purrr)
library(GGally)
library(FactoMineR)
library(factoextra)
library(RColorBrewer)
library(gridExtra)
library(rlang)
library(ggfortify)
library(patchwork)
library(reshape2)
```
Install all dependencies with:
```r
install.packages(c("tidyverse", "janitor", "skimr", "DataExplorer", "ggrepel", 
                   "corrplot", "car", "multcomp", "fastDummies", "lmtest", 
                   "sandwich", "knitr", "tibble", "broom", "purrr", "GGally", 
                   "FactoMineR", "factoextra", "RColorBrewer", "gridExtra", 
                   "rlang", "ggfortify", "patchwork", "reshape2"))
```
---
## Key Findings
- Production factors: Certain studios (e.g., Kyoto Animation), sources (e.g., manga), and types (e.g., TV series) are consistently linked to higher success.
- Clustering: Five interpretable anime production clusters had strong links to genre, source, and studio.
- Modeling: Type and source were significant predictors of anime score even after controlling for PCA dimensions and clustering.
---
# Author
Theodore Gim
University of California
STA 160 – Spring 2025
