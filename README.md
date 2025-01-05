# NBA Game Winner Prediction Project

## Overview
This project predicts the winner of an NBA game based on player attribute ratings from the NBA 2k game. It consists of three primary workflows: collecting game and player data, training and testing a machine learning model (random forest), and using the trained model to predict game outcomes. Below is a detailed explanation of the project files and their usage.  The model's predictive assessment metric scores tested in the high 60s to low 70s range.  Dashboard link: https://taipy-dashboard-1018899736558.us-central1.run.app/

---

## Project Files

### 1. **Model Training and Testing: `Modeling.ipynb`**
   - **Purpose**: Train and evaluate a machine learning model to predict game winners.
   - **Contents**:
     - **Feature Scaling**: Uses `MinMaxScaler` to normalize player and team attributes.
     - **Model Selection**: Trains a Random Forest model to classify game outcomes.
     - **Evaluation**: Assesses the model's performance using metrics such as accuracy, precision, recall, F1 score, and ROC-AUC.
     - **Cross-Validation**: Implements k-fold cross-validation to ensure robust performance.
   - **Outputs**:
     - Serialized model: `rf_model.pkl`.
     - Serialized scaler: `scaler.pkl`.

### 2. **Prediction: `NBA_Game_Winner_Predictor.ipynb`**
   - **Purpose**: Predict the winner of a game based on two teams' starting players.
   - **Contents**:
     - Loads the trained model (`rf_model.pkl`) and scaler (`scaler.pkl`).
     - Accepts inputs for the starting players of two teams.
     - Fetches player attributes from `league.json`.
     - Computes average attributes for each team, scales them using the pre-trained scaler, and makes a prediction.
   - **Output**: A prediction indicating whether Team 0 or Team 1 is expected to win.


---

## Requirements
- Python 3.7+
- Jupyter Notebook
- Libraries:
  - `nba_api`
  - `pandas`
  - `scikit-learn`
  - `matplotlib`
  - `pickle`

---

## Future Work
- I plan on incorporating backup players into the model by using weighted averages, giving starters higher weight.


