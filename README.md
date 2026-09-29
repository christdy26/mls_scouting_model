# MLS Scouting Model

An exploratory Python notebook for identifying promising under-24 Major League Soccer players using scoring and playmaking statistics.

## What it does

The notebook explores player performance in two phases:

1. Filters players to age 24 or younger with at least 450 minutes played and calculates non-penalty goals per 90 minutes.
2. Combines non-penalty goals per 90 with progressive passes per 90, then uses their sum as a simple threat score to rank prospects.
3. Visualizes the player pool and highlights leading candidates by position.

The combined score is a basic exploratory ranking. It adds the two per-90 measures with equal weight; it is not a validated prediction or a club-specific fit model.

## Tools

- Python
- pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

## Data and running the notebook

The repository contains `mls_data.ipynb`; the source CSV and Excel data files are not included. The notebook expects player statistics with fields such as player, position, age, minutes, 90s, and non-penalty goals, plus a progressive-passes measure that can be joined by player name.

Install the notebook dependencies:

```bash
pip install pandas matplotlib seaborn openpyxl jupyter
```

Then open `mls_data.ipynb` in Jupyter and provide the required data files locally. Before running all cells, update the file paths to match where the files are stored. The notebook currently uses inconsistent names for the player-statistics CSV in its two phases and references `df_clean` before it is initialized in Phase 1, so those setup points need to be corrected for a clean run from top to bottom.

## Outputs

When run with the required data, the notebook creates a ranked list of up to 50 prospects and position-based scatter plots. The plots are saved as `red_bulls_targets.png` and `highlighted_targets.png` in the notebook's working directory.
