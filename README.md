# ML Exercise Routine

## Overview

This project looks at a simple personal question:

**Does the weather affect whether I go running?**

The analysis combines personal workout history from Fitbod/Nike Run Club with NOAA weather data, then uses machine learning classification models to predict whether a workout day was a run or not.

## Project Description

The notebook cleans and combines workout data with daily weather observations, labels each workout date as either:

- `1` = running workout
- `0` = non-running workout

The project then uses weather variables as model features to test whether conditions like precipitation, snow, snow depth, and max temperature help explain running behavior.

## Data Sources

The project uses two main data sources:

- **Workout data** from Fitbod and Nike Run Club
- **Weather data** from NOAA

Weather features used:

| Feature | Meaning |
|---|---|
| `PRCP` | Precipitation / rain |
| `SNOW` | Snowfall |
| `SNWD` | Snow depth |
| `TMAX` | Maximum temperature |

Target variable:

| Field | Meaning |
|---|---|
| `Day` | Workout date |
| `Label` | Run = 1, Non-run = 0 |

## Methods

The project includes the following steps:

1. Import workout and NOAA weather datasets
2. Filter weather data by relevant stations
3. Clean and structure workout data
4. Create a binary running label
5. Merge workout and weather features by date
6. Train and evaluate classification models
7. Compare model performance using accuracy, F1 score, true positive rate, and true negative rate

## Models Tested

The notebook tests several classification models, including:

- k-Nearest Neighbors
- Logistic Regression
- Random Forest
- Naive Bayes
- Linear Discriminant Analysis
- Quadratic Discriminant Analysis
- Decision Tree
- Support Vector Machine

The presentation focuses mainly on:

- k-Nearest Neighbors
- Logistic Regression
- Random Forest

## Main Findings

The models showed that weather may have some relationship with running behavior, but the dataset was small and uneven, which limited model strength.

Initial model results showed:

| Model | Accuracy | F1 Score | True Positive Rate | True Negative Rate |
|---|---:|---:|---:|---:|
| k-Nearest Neighbors | 73.56% | 82.44% | 86.82% | 34.67% |
| Logistic Regression | 72.88% | 82.97% | 90.91% | 20.00% |
| Random Forest | 75.25% | 84.32% | 94.09% | 14.67% |

After testing only days with precipitation greater than zero, Logistic Regression performed strongest:

| Model | Accuracy | F1 Score | True Positive Rate | True Negative Rate |
|---|---:|---:|---:|---:|
| k-Nearest Neighbors | 74.85% | 81.49% | 87.18% | 50.00% |
| Logistic Regression | 81.52% | 85.74% | 87.18% | 70.00% |
| Random Forest | 78.18% | 69.44% | 64.10% | 60.00% |

## Key Takeaway

The project suggests that weather features can help predict whether a workout day is a running day, but the results should be treated carefully because the dataset is relatively small. More workout history and additional features, such as weekday, season, distance, pace, and workout type, would likely improve the analysis.

## Technologies Used

- Python
- pandas
- NumPy
- scikit-learn
- matplotlib
- Jupyter Notebook

## Files

| File | Description |
|---|---|
| `Final_Workout_v1.ipynb` | Main notebook for data cleaning, modeling, and evaluation |
| `WorkoutExport.csv` | Personal workout export data |
| `MA_weather.csv` | Massachusetts NOAA weather data |
| `UT_weather.csv` | Utah NOAA weather data |
| `In Class Presentation - Slides.pdf` | Project presentation |

## How to Run

1. Clone the repository.

```bash
git clone https://github.com/JaredHutchinson/ML_Exercise_Routine.git
cd ML_Exercise_Routine
```

2. Install the required Python packages.

```bash
pip install pandas numpy scikit-learn matplotlib
```

3. Open the notebook.

```bash
jupyter notebook Final_Workout_v1.ipynb
```

4. Run the notebook cells from top to bottom.

## Notes

The workout data is personal and may need to be removed or anonymized before making the repository fully public.
