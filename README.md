# Chess Opening Analysis with Machine Learning

## Overview

This project uses supervised machine learning to analyze the role of chess opening choices in online games. Using a large dataset of online chess matches, the project investigates two related questions: whether certain openings consistently lead to better game outcomes, and whether opening choice influences how games unfold in terms of length or draw likelihood. Logistic regression and random forest models are used to evaluate both predictive performance and structural effects, with careful attention to feature engineering and data leakage.

Overall, the results show that player rating is the dominant factor in determining game outcomes, while opening choice plays a more meaningful role in shaping game structure, particularly game length and complexity.



## Research Questions

1. Do certain chess openings consistently lead to better outcomes?
2. Do chess openings affect game length or draw likelihood?



## Dataset

The dataset consists of online chess games and includes the following key information:

- Player ratings (White and Black)
- Game outcomes (win, loss, draw)
- Opening information (ECO codes and opening names)
- Time controls
- Number of turns (game length)

Each row represents a single chess game. Only information available at the start of the game or during the opening phase is used for outcome prediction to avoid data leakage.



## Methods

### Feature Engineering
- Rating difference between White and Black players
- Opening depth (opening ply)
- Time control (increment code)
- Opening representation using both ECO families and filtered full ECO codes
- Binary indicators for rated games

### Models Used
- Logistic Regression: baseline classification model for interpretability
- Random Forest (Classification): captures nonlinear relationships in outcome prediction
- Linear Regression: baseline regression model for predicting game length
- Random Forest (Regression): main model for capturing nonlinear effects on game length

### Evaluation Metrics
- Classification: Accuracy and ROC AUC
- Regression: R² and RMSE



## Analysis 1: Openings and Game Outcomes

In the first analysis, classification models were trained to predict whether White wins a game using only pre-game information. Models using player ratings and time control were compared against models that also included opening information.

Key findings:
- Player rating and time control dominate outcome prediction
- Adding opening information does not improve predictive performance
- Apparent opening strength is largely explained by stronger players selecting those openings

Conclusion:  
Chess openings do not independently determine who wins once player skill is accounted for.



## Analysis 2: Openings and Game Structure

The second analysis reframed the problem to examine whether openings influence how games unfold. Game length, measured by the number of turns, was used as a proxy for game structure and complexity.

Key findings:
- Linear regression explains very little variation in game length
- Random Forest regression performs better, indicating nonlinear effects
- Theoretical and positional openings (e.g., Sicilian Najdorf, Ruy Lopez structures) are associated with longer games
- Tactical or irregular openings tend to result in shorter games

Conclusion:  
While openings do not strongly predict outcomes, they meaningfully influence game length and structure.

## Conclusion

This project investigated whether chess opening choice meaningfully influences game outcomes and 
game structure using machine learning models applied to a large dataset of online chess 
games. Initial classification models showed that player rating and time control were the dominant 
predictors of game outcome, while opening choice whether represented by ECO families or full 
ECO codes did not improve predictive performance once player skill was controlled for. 
This suggests that openings do not independently determine who wins a game, and that their apparent 
effectiveness is largely explained by stronger players selecting stronger openings.

Given these findings, the analysis was reframed to examine whether openings influence how games unfold, 
rather than who wins. Treating game length (number of turns) as a regression problem revealed more 
meaningful patterns. While a linear regression model explained very little variation in game length, 
a Random Forest regressor captured nonlinear relationships and performed better, indicating that 
opening choice contributes to game structure in more complex ways. Descriptive analysis supported 
these results, showing that theoretical and positional openings such as the Sicilian Najdorf, 
Ruy Lopez variations, and Slav structures are associated with longer games, while 
irregular or tactical openings tend to result in shorter, more decisive games.

Overall, the results suggest that chess openings shape the character of a game rather than 
its final result. Player strength remains the primary determinant of winning, but opening choice 
plays a meaningful role in influencing game length and complexity. This highlights the importance 
of careful problem framing in data science: while some factors may not predict outcomes directly, 
they can still exert a significant influence on underlying structure and dynamics.

## Key Takeaways

- Player rating is the strongest predictor of chess game outcomes
- Opening choice does not significantly improve win prediction beyond player skill
- Openings shape the structure of games rather than determining winners
- Nonlinear machine learning models are necessary to capture structural effects
- Proper problem framing is critical when applying machine learning to real world data



## Visualizations

The project includes:
- Model performance comparisons
- Bar charts showing openings associated with longer and shorter games
- Distributions of game length illustrating prediction difficulty

These visualizations are used for both exploratory analysis and presentation.


## Technologies Used

- Python
- pandas
- scikit-learn
- matplotlib

## Author
Exequiel Fleitas

