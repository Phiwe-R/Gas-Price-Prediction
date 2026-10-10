# Natural Gas Price Prediction and Storage Contract Valuation

## Project Overview

This project uses Python to predict natural gas prices and estimate the value of a natural gas storage contract.

The project has two parts:
1. **Gas Price Prediction:** Use past gas prices to predict prices for a chosen date.
2. **Storage Contract Valuation:** Use the predicted prices to estimate how much profit a gas storage contract could make after costs.

## Part 1: Natural Gas Price Prediction

Natural gas prices change over time. They can also follow seasonal patterns, with prices rising and falling during different times of the year.

In this part, I:
- Load and clean the historical gas price data.
- Plot the prices to see how they change over time.
- Use **sine and cosine** to help the model learn yearly price patterns.
- Train a **Linear Regression** model using time and the seasonal patterns.
- Create a function that predicts the gas price for a given date.

For example, the notebook tests a prediction for **30 May 2025**.

## Part 2: Natural Gas Storage Contract Valuation

The second part uses the price prediction model to estimate the value of a gas storage contract.

The idea is to **buy and store gas when prices are lower**, then **sell it when prices are higher**.

The calculation considers:
- Predicted prices when gas is bought (injected into storage).
- Predicted prices when gas is sold (withdrawn from storage).
- Amount of gas bought and sold.
- Storage costs.
- Injection and withdrawal costs.
- Transport costs.

The estimated contract value is calculated as:

**Contract Value = Sales Revenue − Gas Purchase Cost − Storage Cost − Injection Cost − Withdrawal Cost − Transport Cost**

The notebook includes an example that buys gas in July 2024 and sells it in January 2025.

## Tools and Libraries

- **Python** – Programming language
- **Pandas** – Working with data and dates
- **NumPy** – Calculations and seasonal patterns
- **Matplotlib** – Plotting gas prices
- **Scikit-learn** – Building the Linear Regression model
- **Jupyter Notebook** – Running the project step by step

## How to Run the Project

1. Download or clone this repository.
2. Make sure the `nat_gas.ipynb` notebook and `Nat_Gas.csv` dataset are in the same folder.
3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn notebook
   ```

4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `nat_gas.ipynb` and run the cells from top to bottom.

The dataset must contain two columns: `Dates` and `Prices`. The notebook reads dates in `MM/DD/YY` format.

## Example Usage

After running the model training cells, you can predict a price with:

```python
estimate_price('2025-05-30')
```

You can also change the dates, gas volumes, and costs in the `price_storage_contract()` example to estimate a different contract value.

## Important Notes

- The gas prices and contract values are **estimates**, not guaranteed future results.
- The contract function prints a warning if the total injected gas is above the maximum storage capacity, but it does not stop the calculation.
- The `Nat_Gas.csv` file is needed to run the notebook. Add it to the repository if you have permission to share it.

## Project Goal

The goal of this project is to practise using **data analysis, machine learning, and Python** to solve a real-world financial problem.
