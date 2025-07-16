# 🧾 DeFi Credit Scoring Using Machine Learning

A lightweight machine learning pipeline that assigns credit scores to DeFi wallet addresses based on on-chain transaction behavior. It’s simple, fast, and fully open-source — no centralized credit bureaus needed.

---

## 📌 Project Summary

This project analyzes DeFi transactions (e.g. Aave v2 deposits on Polygon) to extract user behavior and compute a **credit score from 0 to 1000** per wallet. The model is trained using unsupervised clustering to simulate risk categories, followed by a supervised learning model to generalize the scoring logic.

---

## 🚀 What It Does

✅ Loads wallet-level DeFi transaction data  
✅ Extracts key behavioral features  
✅ Clusters users into risk profiles (e.g. low, mid, high risk)  
✅ Trains a machine learning model (Random Forest)  
✅ Outputs interpretable credit scores for each wallet  

---

## 💡 Example Output

| Wallet Address                         | Credit Score |
|----------------------------------------|--------------|
| `0x0000...b6d4b6`                      | 861          |
| `0x0000...18da6`                       | 612          |
| `0x0000...a12e7`                       | 389          |

---

## 🧠 Features Engineered

- `total_tx_count` – Number of on-chain actions  
- `total_deposit_usd` – Total value deposited in USD  
- `avg_deposit_usd` – Average deposit size  
- `asset_diversity` – Number of different tokens used  
- `activity_days` – Number of unique active days  
- `account_age_days` – Age of the wallet (based on transactions)  
- `tx_frequency` – Transactions per active day  

---

## 📊 Score Distribution

The model assigns scores between **0 (high risk)** and **1000 (low risk)**. Most users tend to fall into a healthy middle range, but extremes reflect risky or inactive behavior.

---

## 📁 Project Structure

