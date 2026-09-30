# 📈 Trader Artificial Intelligence

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Deep Learning](https://img.shields.io/badge/Deep_Learning-TensorFlow%20%7C%20Keras-orange?logo=tensorflow)
![Comet ML](https://img.shields.io/badge/Experiment_Tracking-Comet_ML-blueviolet)
![Status](https://img.shields.io/badge/Status-Active_Development-success)

A personal student project built for learning and experimentation in Deep Learning applied to algorithmic trading. This repository represents my learning journey through various quantitative modeling paradigms, emphasizing data engineering, risk management, and experimenting with neural network architectures rather than building a professional product.

## 🚀 Overview

**Trader Artificial Intelligence** is an educational project aimed at building a machine learning pipeline to analyze technical indicators and predict price action. It features a complete ML workflow—from financial data ingestion and preprocessing to model training, experiment tracking, and custom backtesting.

## 🧠 Machine Learning Pipeline & Technical Approach

A key learning objective of this project was to understand and avoid common pitfalls in financial ML, such as lookahead bias and data leakage, while evaluating simulated profitability.

*   **Feature Engineering:** Use of `pandas_ta` to generate a set of technical indicators.
*   **Robust Normalization:** Implementation of a strict rolling mean normalization strategy. This ensures that the model only sees past data during training, aimed at eliminating **lookahead bias**.
*   **Synthetic Label Generation:** Labels are synthetically generated to reflect a simplified version of **actual profitability**, factoring in:
    *   0.1% simulated exchange fees per trade.
    *   Maximum drawdown constraints to model risk tolerance.
*   **Imbalance Handling:** The pipeline includes basic mechanisms to handle class imbalance, preventing the model from just predicting the majority class.
*   **Experiment Tracking:** Integrated with **Comet ML** to log hyperparameters, visualize metrics, and track model lineage across training iterations.
*   **Custom Backtesting Engine:** The system uses a custom backtester that applies temporal smoothing to the model's softmax probability outputs, attempting to create more stable trade executions in simulation.

## 📖 History & Problems Solved

This project evolved through trial, error, and continuous learning:

1.  **The Baseline (Linear Regression):** The exploration initially began with simple linear regression models to predict continuous price changes. It quickly became evident how non-linear and noisy financial markets are.
2.  **The Pivot to Deep Learning:** Shifting to deep learning allowed for capturing more complex relationships in the data.
3.  **The First Iteration (CNN/GRU):** The initial implementation of a combined Convolutional Neural Network (CNN) and Gated Recurrent Unit (GRU) architecture struggled. Despite okay theoretical metrics, it resulted in a **negative yield of -36%** in simulated trading.
4.  **The Breakthrough:** This failure drove a redesign of the architecture and data pipeline. By introducing rolling normalization, fee-aware synthetic labels, and probability smoothing, the simulation became much more realistic, providing valuable lessons in financial ML.

## 🔮 Future Roadmap

As an academic exploration, the next phase of development focuses on predicting market regimes:

*   **Hybrid Architecture:** Researching and implementing a hybrid **CNN + GRU + XGBoost** architecture, inspired by recent quantitative finance papers.
*   **Market Regime Prediction:** The XGBoost component will be trained to classify the overarching market regime (e.g., high volatility, trend-following), attempting to dynamically gate and weight the predictions of the deep learning layers.

---
*A student's exploration into algorithmic trading and deep learning.*
