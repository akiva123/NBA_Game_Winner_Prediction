# NBA Game Winner Prediction Project

## Overview
This project predicts the winner of an NBA game based on player attribute ratings from the NBA 2k game. It consists of three primary workflows: collecting game and player data, training and testing a machine learning model, and using the trained model to predict game outcomes. Below is a detailed explanation of the project files and their usage.  The model's predictive assessment metric scores tested in the 80-90% range.

---

## Project Files

### 1. **Data Collection: `Get_Data_from_NBAapi.ipynb`**
   - **Purpose**: Retrieve game data and player statistics from the NBA API.
   - **Contents**:
     - Connects to the NBA API to fetch the 5 starters for each team of each game for the 23-24 season.
     - Processes the data into a structured format suitable for modeling.
   - **Output**: A CSV file containing features such as average team player ratings and game outcomes.

### 2. **Model Training and Testing: `Training&Testing_Model.ipynb`**
   - **Purpose**: Train and evaluate a machine learning model to predict game winners.
   - **Contents**:
     - **Feature Scaling**: Uses `MinMaxScaler` to normalize player and team attributes.
     - **Model Selection**: Trains a Random Forest model to classify game outcomes.
     - **Evaluation**: Assesses the model's performance using metrics such as accuracy, precision, recall, F1 score, and ROC-AUC.
     - **Cross-Validation**: Implements k-fold cross-validation to ensure robust performance.
   - **Outputs**:
     - Serialized model: `rf_model.pkl`.
     - Serialized scaler: `scaler.pkl`.

### 3. **Prediction: `NBA_Game_Winner_Predictor.ipynb`**
   - **Purpose**: Predict the winner of a game based on two teams' starting players.
   - **Contents**:
     - Loads the trained model (`rf_model.pkl`) and scaler (`scaler.pkl`).
     - Accepts inputs for the starting players of two teams.
     - Fetches player attributes from `league.json`.
     - Computes average attributes for each team, scales them using the pre-trained scaler, and makes a prediction.
   - **Output**: A prediction indicating whether Team 0 or Team 1 is expected to win.

### 4. **Serialized Files**
   - **`rf_model.pkl`**:
     - The trained Random Forest model used for predictions.
   - **`scaler.pkl`**:
     - The MinMaxScaler used to normalize features during model training.


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
I plan on incorporating backup players into the model by using weighted averages, giving starters higher weight.

