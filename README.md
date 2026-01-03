# Chess Opening Analysis with Machine Learning
This project uses supervised machine learning to analyze the impact of chess opening choices on game outcomes and game structure. Using a large dataset of online chess games, we first investigate whether certain openings consistently lead to better outcomes after controlling for player rating and time control. We then examine whether opening choice affects how games unfold by modeling game length and draw likelihood. Logistic regression and random forest models are used to evaluate both predictive performance and structural effects. The results show that while player skill dominates win prediction, opening choice meaningfully influences game length and complexity, particularly through nonlinear patterns.

## Research Questions
1. Do certain chess openings consistently lead to better game outcomes?
2. Do chess openings affect game length or draw likelihood?

## Dataset
Online chess game data including player ratings, openings (ECO codes), time controls, outcomes, and game length.

## Methods
- Logistic Regression (baseline classification)
- Random Forest (classification and regression)
- Feature engineering with rating differences and ECO codes
- Leakage-aware modeling

## Analysis 1: Opening Choice and Game Outcomes
- Ratings-only vs. ratings & opening models
- ECO family and full ECO comparisons
- Result: openings do not significantly improve win prediction beyond player skill

## Analysis 2: Opening Choice and Game Structure
- Regression modeling of game length (turns)
- Random Forest captures nonlinear opening effects
- Result: openings influence game length and complexity, though effects are modest

## Key Takeaways
- Player rating is the strongest predictor of game outcomes
- Opening choice shapes how games unfold, not who wins
- Nonlinear ML models are necessary to capture structural effects

## Technologies
Python, pandas, scikit-learn, matplotlib
