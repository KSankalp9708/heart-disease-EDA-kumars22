# Exploratory Data Analysis (EDA) of Heart Disease 

## Objective

- Explore clinical variables in **heart.csv** and their relationship with HeartDisease (0/1).
- Visualize **distributions**, **class balance**, and **pairwise relationships** to guide feature understanding and future modeling.

## Approach
- *Data & Libraries*: pandas, numpy, seaborn
- *Load & Preview*: Read heart.csv, inspect top rows
- *Categorical Analysis* (pie charts): Gender, ChestPain type, RestingECG type, ST slope type, HeartDisease
- *Distributions* (seaborn displot + KDE): Age, RestingBP, Cholesterol, MaxHR
- *Violin Plots* (by HeartDisease): Age, Sex vs HeartDisease, Age vs HeartDisease, Cholesterol vs HeartDisease
- *Correlation* & *Heatmap*: Compute correlation matrix for Age, RestingBP, Cholesterol, FastingBS, MaxHR, Oldpeak, HeartDisease; visualize with sns.heatmap
- *Pairplots*:
  - 'Age' vs 'HeartDisease'
  - 'Age'vs 'RestingBP' vs 'HeartDisease' (with hue = 'HeartDisease')
  - 'Age' vs 'Cholesterol' vs 'FastingBS' vs 'HeartDisease' (with hue = 'HeartDisease')
  - 'Age' vs 'MaxHR' vs 'Oldpeak' vs 'HeartDisease'
  - Full numeric dataframe
- *Jointplots*:
  - Age vs MaxHR (hexbin)
  - Age vs Cholesterol (scatter)
  - RestingBP vs MaxHR (hexbin)

## Results / Insights

- Gender Distribution: ~79% of patients are male, ~21% female, showing a higher representation of male patients.
- Heart Disease Prevalence: Around 55% of individuals in the dataset are labeled 1 (heart disease present), indicating a slightly imbalanced target class.
- Chest Pain Types: ASY (Asymptomatic) pain dominates at ~54%, followed by ATA, NAP, and TA.
- Age Profile: Most patients fall between 40–60 years, peaking in late 50s (violin plot); risk incidence rises notably with age.
- Cholesterol & Resting BP: Cholesterol values show a wide spread; a notable portion of patients have high cholesterol (>240 mg/dl). Resting BP clusters around 120–150 mmHg.
- Max HR: The maximum heart rate varies a lot around 100-180 bpm.
- ST Slope: Flat ST slope is strongly associated with positive heart disease labels.
- Correlation Findings: Strongest positive correlation is between Oldpeak and HeartDisease(~ 0.4), and a negative correlation between MaxHR and disease incidence(~ -0.4).

- Relationships (Pairplots):
  - 'HeartDisease' presence tends to be more dependent on 'Age' than 'RestingBP'.
  - 'Normal-to-High' level of cholesteral seems to dominate in age groups with heart disease, while '0' cholesteral level is pre-dominant in such lower age groups.
  - Patients with high Oldpeak and RestingBP exhibit higher heart disease prevalence.

- Relationships (Jointplots):
  - The Age-group between 50-60 are most likely have high maximum Heart-Rate, ranging from '120-160' bpm.
  - 'MaxHR' varies a lot (100-180 bpm) w.r.t. normal resting blood pressure(120-140 mmHg).
