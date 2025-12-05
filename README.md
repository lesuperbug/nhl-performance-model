# NHL Player Performance Modelling

This project builds machine-learning models to predict NHL player performance using multiple seasons of historical data. The primary target variable is a per-game production metric (e.g. fantasy points per game, “FP/G") constructed from goals, assists, shots, and other box-score stats. The target variable is the the combined score of all the box-score stats used in the relevant league as per the scoring rules of said fantasy league. The aim is to predict player performance for the upcoming season based on past seasons, allowing for applications in fantasy hockey or sports betting.

The modelling pipeline trains and compares a range of regression algorithms, including linear regression, regularized regression, support vector regression, random forests, and gradient-boosted trees. Models are evaluated using MSE (training vs test sets), and the best-performing model is used to generate predictions for the upcoming season. The focus is on clean feature engineering, transparent model comparison, and out-of-sample evaluation.

---

## Data & Features

- **Input data**: season-level CSVs stored in the `Modelling Data/` folder  
  - Each file corresponds to a single NHL season (e.g. `2017-18.csv`, `2018-19.csv`, …).  
  - Files share a common schema with an `ID` column and multiple predictor variables.
- **Target variable**: a per-game production metric (e.g. `FP/G`) specified via `y_var_name`.
- **Features**:
  - Counting stats: goals, assists, shots, corsi, etc.
  - Usage metrics: TOI, PP minutes.

The code aggregates multiple seasons, builds a training set from historical seasons, and constructs a prediction set for the upcoming season.