# Primetrade.ai Data Science Intern - Round 0 Assignment

This repository contains my submission for the Data Science Internship evaluation. The analysis uncovers patterns relating market sentiment (Fear/Greed) to trader behavior and performance on the Hyperliquid platform.

## Repository Contents

*   `data/`: Directory intended for the `sentiment.csv` and `hyperliquid.csv` files.
*   `analysis.ipynb`: The primary Jupyter Notebook containing the data preparation, analysis, metrics formulation, and visualization steps.
*   `report.md`: A 1-page write-up summarizing the methodology, insights, and actionable trading rules.
*   `*.png`: The resulting charts used as evidence to back up our insights.

## Setup and How to Run

1.  **Clone the repository:**
    ```bash
    git clone <repository_url>
    cd primetrade-assignment
    ```

2.  **Add Datasets:**
    Ensure that the two datasets (`sentiment.csv` and the historical trader data renamed to `hyperliquid.csv`) are placed within the `data/` subdirectory.

3.  **Environment Setup:**
    Create a Python virtual environment and install the required dependencies:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    pip install pandas numpy matplotlib seaborn jupyter
    ```

4.  **Execute Analysis:**
    Launch Jupyter and open the notebook to view or re-run the analysis:
    ```bash
    jupyter notebook analysis.ipynb
    ```
    Alternatively, you can run all cells head-to-tail to reproduce the metrics and charts.
