# Exploratory Data Analysis & Reproducible Data Pipeline
✨ Overview

This repository contains my work for Task-1 (EDA & Statistical Analysis) and Task-2 (DVC Setup) of the KAIM program.
These tasks focus on building a strong analytic foundation, understanding the dataset in depth, and establishing a reproducible data workflow using Data Version Control (DVC) — a standard in regulated industries like finance and insurance.

The work here reflects not only analysis but discipline, precision, and a commitment to auditability.

🌱 Task 1 — Exploratory Data Analysis (EDA)

Before models, we listen. Before predictions, we explore.

This task focuses on uncovering the hidden patterns within the dataset, understanding data quality, and building statistical intuition for risk and profitability forecasting.

🔍 Objectives

Develop a deep understanding of the dataset

Assess data quality and structure

Compute descriptive statistics

Visualize key insights

Detect patterns in loss ratios, vehicle types, geographies, and more

Support insights with appropriate statistical thinking

📁 Dataset

File: MachineLearningRating_v3.txt
Format: Pipe-delimited (|)
Columns include: Customer details, vehicle parameters, premium amounts, claims history, cover types, provinces, and more.

🧪 Analytical Guiding Questions

These questions shaped the EDA:

1. Loss Ratio Analysis

What is the overall Loss Ratio:
TotalClaims / TotalPremium

How does this vary by:

Province

VehicleType

Gender

2. Distributions & Outliers

What do the distributions of TotalPremium, TotalClaims, CustomValueEstimate look like?

Are there outliers that could distort insights?

3. Temporal Trends (18 months)

How did claim frequency/severity change over time?

Are there seasonal or monthly risk patterns?

4. Vehicle Risk Patterns

Which makes/models show high or low claim amounts?

Are certain types inherently riskier?

📊 EDA Activities Completed
🔹 Data Summarization

Loaded and cleaned dataset

Converted dates, categoricals, numericals

Generated descriptive stats (mean, std, skewness, IQR)

🔹 Data Quality Checks

Missing value detection

Duplicate checks

Format inconsistencies

Noise/outlier detection using boxplots

🔹 Univariate Analysis

Histograms (TotalPremium, TotalClaims, SumInsured, CustomValueEstimate)

Bar charts for categorical variables (Gender, Province, VehicleType)

🔹 Bivariate / Multivariate

Loss Ratio by Province, VehicleType, Gender

Correlation matrix of financial variables

Scatter plots of Premium vs Claims

Premium/Claims trends across PostalCode regions

🔹 Geographic Comparisons

Differences in CoverType, Premium, Make/Model across Provinces

Risk patterns across Cresta Zones

🔹 Creative Visualizations (3+ plots)

Custom aesthetic visualizations capturing:

Geographic risk flow

Premium vs Claims dynamics

High-risk vehicle categories

🌿 Task 2 — Reproducible Data Pipeline with DVC

Because true data science must always be traceable, transparent, and accountable.

Financial and insurance analytics require strong auditability.
DVC ensures that every dataset used in analysis is versioned, traceable, and reproducible — just like code.

⚙️ Task 2 Objectives

Install and configure DVC

Set up a local remote storage

Add raw data to DVC tracking

Push data to local remote

Maintain clean reproducible data workflow

Create and merge Git branches for structured project tracking

🛠️ DVC Setup Steps
1. Install DVC
pip install dvc

2. Initialize DVC
dvc init

3. Create Local Remote Storage
mkdir dvc_storage

4. Add Remote to DVC
dvc remote add -d localstorage ./dvc_storage

5. Add Raw Data to DVC

(Only original raw data — not metadata or processed files)

dvc add data/raw/MachineLearningRating_v3.txt

6. Commit to Git
git add .
git commit -m "Add raw dataset tracked with DVC"

7. Push Data to Remote
dvc push

🌿 Branching & Version Control Requirements
From Task 1

Branch created: task-1

Regular commits with meaningful messages

Merged into main using Pull Request

For Task 2

New branch: task-2

Commits documenting:

DVC installation

Remote setup

Raw data tracking

DVC push operations

🧭 Directory Structure

A clean and auditable project layout:

project/
│
├── data/
│   ├── raw/
│   │   └── MachineLearningRating_v3.txt
│   ├── processed/
│   └── interim/
│
├── eda/
│   └── eda_analysis.ipynb
│
├── dvc_storage/      ← Local DVC remote
│
├── .dvc/             ← DVC internal files
│
├── README.md
└── requirements.txt
