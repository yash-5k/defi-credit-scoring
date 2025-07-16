# DeFi Credit Scoring

Assigning behavioral credit scores to DeFi wallets using transaction history and machine learning.

---

## 🚀 Overview

This project analyzes user wallet activity on the Polygon network (e.g. Aave V2 deposits) to generate a **credit score between 0 and 1000** for each address. The scores reflect behavioral patterns like activity frequency, asset diversity, and transaction volume—serving as a lightweight proxy for creditworthiness in DeFi.

The final model is trained using **unsupervised clustering** to simulate wallet risk profiles, and then a **supervised ML model** generalizes this logic for scalable prediction.

---

## 🧠 Key Features

- Parses raw DeFi transaction JSON into wallet-level summaries
- Extracts behavioral features (e.g., frequency, amount, token variety)
- Uses **KMeans** to simulate risk buckets (unsupervised labels)
- Trains a **Random Forest Regressor** to predict credit scores
- Outputs a clean CSV with wallet addresses + score

---

## 📊 Sample Credit Score Output

| Wallet Address                         | Credit Score |
|----------------------------------------|--------------|
| 0x00000000001accfa9cef68cf5371a23025b6d4b6 | 812          |
| 0x000000000051d07a4fb3bd10121a343d85818da6 | 677          |

---

## 🛠️ How It Works

### 1. Preprocessing
- Loads `user-wallet-transactions.json`
- Converts token amounts to USD
- Groups transactions by wallet

### 2. Feature Engineering
Extracted per wallet:
- `total_tx_count`
- `total_deposit_usd`
- `avg_deposit_usd`
- `asset_diversity`
- `activity_days`
- `account_age_days`
- `tx_frequency`

### 3. Modeling
- Cluster wallets with **KMeans** to define simulated credit levels
- Train a **RandomForestRegressor** to learn score boundaries
- Score range: `0–1000` (higher = better behavior)

---

## 📂 File Structure

