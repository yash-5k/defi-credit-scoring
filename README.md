# DeFi Credit Scoring

Assigning behavioral credit scores to DeFi wallets using transaction history and machine learning.

---

## 🧠 What Is This?

This project analyzes historical transactions from DeFi protocols (like Aave V2 on Polygon) to generate a **credit score (0–1000)** for each wallet.

The idea: If traditional finance has FICO, then DeFi should have something smarter—built on real, on-chain behavior.

---

## 🧱 System Architecture

![DeFi Credit Scoring Architecture](docs/architecture.png)

*Figure: End-to-end flow from raw JSON to scored wallets*

---

## 🧮 Feature Engineering Pipeline

![Feature Extraction](docs/features.png)

*Figure: How we summarize user behavior into ML features*

---

## 📈 Sample Score Distribution

![Credit Score Distribution](docs/score-distribution.png)

> Scores cluster around behavior profiles, ranging from low-risk to suspicious wallets.

---

## 📊 Example Output

| Wallet Address                         | Credit Score |
|----------------------------------------|--------------|
| 0x00000000001accfa9cef68cf5371a23025b6d4b6 | 812          |
| 0x000000000051d07a4fb3bd10121a343d85818da6 | 677          |

---

## 🔍 How It Works

1. **Load & parse JSON transaction history**
2. **Engineer wallet-level features** (frequency, size, token diversity, etc.)
3. **Cluster** wallets with KMeans (to simulate risk buckets)
4. **Train Random Forest Regressor** on features + cluster ranks
5. **Score new wallets** between 0 (high risk) to 1000 (low risk)

---


