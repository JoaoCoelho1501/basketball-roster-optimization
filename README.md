# Basketball Roster Optimisation — Integer Linear Programming

An optimisation project using binary decision variables and Gurobi to select a five-player starting lineup from a set of 18 Boston Celtics players under budget and positional constraints.

**Academic context:** MSc in Business Intelligence & Analytics, ISCAP (2025/26)  
**Authors:** Beatriz Teixeira, João Coelho, João Vasques, and Rui Parada

## Problem statement

The objective is to select **five players from a pool of 18** while maximising the aggregate player rating, subject to the constraints defined in the project:

- Total per-game bonus budget of no more than **$1 million**.
- No more than two selected players per position.
- At least one Power Forward.
- Exclude candidates with a score below 0.25.

The player overall score is calculated from selected statistics and normalised using MinMaxScaler.

## Optimisation approach

The problem is formulated as a **Binary Integer Linear Programming (BILP)** model:

- A binary decision variable indicates whether each player is selected.
- The objective function maximises the total weighted player score.
- Constraints enforce lineup size, budget, positional limits, and eligibility.

The model is solved with Gurobi through the `gurobipy` Python interface.

## Why optimisation matters

Selecting the five players with the highest individual ratings is not necessarily optimal when budget and roster composition constraints apply. Mathematical optimisation evaluates feasible combinations and identifies the best solution under the model's assumptions.

## Technology stack

- Python and pandas
- scikit-learn (MinMaxScaler)
- Gurobi Optimizer and gurobipy
- Google Colab

## Running the notebook

1. Open the notebook in Google Colab.
2. Upload `Celtic_Stats.csv` when prompted; the expected delimiter is a semicolon (`;`).
3. Ensure that Gurobi is available and that an appropriate licence is configured.
4. Run the notebook cells to prepare the data, formulate the model, and solve the optimisation problem.

## Scope and limitations

- The selected lineup depends on the input data, score construction, and constraints chosen for the exercise.
- A normalised overall score is a modelling assumption and may not capture every aspect of player contribution.
- The result is an optimisation exercise, not a prediction of actual match outcomes.
- Gurobi licensing requirements apply.
