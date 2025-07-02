# IV Surface Prediction using Deep Learning

## Project Objective
Forecast next-time-slice Implied Volatility (IV) surfaces for BTC options using historical surface data and deep learning models. In quantitative finance, IV surfaces are crucial for pricing, hedging, and relative value trading. This project predicts surface evolution using real-world BTC option data from Deribit.

## Modeling Approach
- Structured raw Deribit options data into interpolated (moneyness × tenor) IV surfaces at 1-minute frequency
- Created time-sequences of surfaces to train models that forecast the next snapshot
- Compared:
  - Dense model (baseline)
  - Conv1D + LSTM
  - Conv2D (spatial-only)

## Results

| Model           | RMSE     |
|----------------|----------|
| Dense          | ~0.16    |
| Conv2D         | ~0.14    |
| Conv1D + LSTM  | **0.1356** (Best) |

## Files
- `IV_Surface_Prediction.ipynb`: Full notebook
- `data.csv`: Source file (from [Kaggle Deribit dataset](https://www.kaggle.com/datasets/hsergeyfrolov/deribit-btc-options-information/data))
