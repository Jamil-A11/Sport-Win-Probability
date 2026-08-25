# Sport-Win-Probability
Creating a win probability model for NFL and Baseball games
# 🏈 NFL Win Probability Model

A machine learning project that predicts **play-by-play win probability** for NFL games, trained on 165,000+ plays across 4 seasons (2022-2025).

## 📌 Project Overview

This project builds a win probability model from scratch using real NFL play-by-play data. Given any game state - score differential, time remaining, down, distance, field position - the model outputs the probability that the possession team wins.

Two models are built and compared:
- **Logistic Regression** - simple baseline model
- **XGBoost** - advanced gradient boosting model

The models are then applied to two of the most dramatic comeback games in NFL history to produce interactive win probability charts.

## 📊 Results

| Model | Accuracy | Log Loss |
|---|---|---|
| Logistic Regression | 55.4% | 0.6874 |
| XGBoost | 73.8% | 0.4926 |

XGBoost achieves an **18.4 percentage point improvement** in accuracy and a **0.196 reduction in log loss** over the baseline.

## 🏟️ Portfolio Charts

### Vikings vs Colts - December 17, 2022
**The biggest comeback in NFL history**

Minnesota Vikings overcame a 33-0 halftime deficit to win 39-36 in overtime - the largest comeback in NFL history. The win probability chart shows Minnesota's line crashing to near 0% at halftime before an extraordinary second half recovery.

### Seahawks vs Rams - December 18, 2025 (Week 16)
**38-37 OT - NFL.com's #1 game of the 2025 season**

Seattle Seahawks trailed 30-14 with under 14 minutes remaining before mounting one of the most dramatic comebacks in recent NFL history, winning in overtime on a two-point conversion.

## 🔧 Features Used

| Feature | Description |
|---|---|
| `score_differential` | Current score margin for possession team |
| `game_seconds_remaining` | Seconds left in the game |
| `score_x_time` | Interaction term - score x time remaining |
| `down` | Current down (1st, 2nd, 3rd, 4th) |
| `ydstogo` | Yards needed for a first down |
| `yardline_100` | Field position (yards from end zone) |
| `posteam_timeouts_remaining` | Timeouts left for possession team |
| `is_home` | Whether possession team is the home team |

## 📁 Project Structure

```
sport-win-probability/
│
├── nfl_winprob.ipynb       # Main notebook - full pipeline
└── README.md               # This file
```

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Jamil-A11/Sport-Win-Probability.git
cd Sport-Win-Probability
```

**2. Install dependencies**
```bash
pip install pandas numpy plotly scikit-learn xgboost pybaseball pyarrow
```

**3. Open the notebook**
```bash
jupyter notebook nfl_winprob.ipynb
```

**4. Run all cells in order**

The notebook will automatically download NFL play-by-play data from the nflverse data repository - no manual data download required.

## 📦 Data Source

NFL play-by-play data is sourced directly from the **nflverse** open data repository:

```
https://github.com/nflverse/nflverse-data
```

Seasons loaded: 2022, 2023, 2024, 2025
Total plays: 165,000+

## 🛠️ Tools & Libraries

- **Python 3.13**
- **pandas** - data manipulation
- **NumPy** - numerical operations
- **scikit-learn** - logistic regression, train/test split, evaluation metrics
- **XGBoost** - gradient boosting model
- **Plotly** - interactive win probability charts
- **VS Code + Jupyter** - development environment

## 📈 What is Win Probability?

Win probability answers: *given the current game state, what is the probability that Team A wins?*

It updates on every play as the game progresses. A good win probability model:
- Starts near 50% for both teams at kickoff
- Moves dramatically in response to scoring plays
- Approaches 100% or 0% as time runs out and the lead becomes insurmountable
- Is well **calibrated** - when the model says 70%, teams win approximately 70% of the time

## 🔮 Future Work

- [ ] Baseball win probability model using Statcast data
- [ ] Model calibration curve analysis
- [ ] Comparison against ESPN win probability benchmarks
- [ ] Extended training data back to 2018
- [ ] Interactive web dashboard using Streamlit

## 👤 Author

**Jamil Ahmed**
- GitHub: [@Jamil-A11](https://github.com/Jamil-A11)
- LinkedIn: [linkedin.com/in/jamilahmed](https://linkedin.com/in/jamilahmed)
