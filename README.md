# DeFi-Credit-Scoring
This project aims to assign credit scores (0–1000) to DeFi wallets based solely on on-chain behavior in the Aave V2 lending protocol. The system analyzes historical transactions like deposits, borrows, repayments, redemptions, and liquidations to derive wallet responsibility, risk levels, and potential bot-like patterns.
# Objective
To design a responsible-usage credit scoring system for wallets interacting with Aave V2. Higher scores indicate trustworthiness; lower scores imply bot activity, high risk, or exploitative behaviors.
# Architecture Overview
## Data Source:
•JSON file of 100K Aave V2 transactions per wallet
 
•Actions include: deposit, borrow, repay, redeemUnderlying, liquidationCall
## Pipeline:
Raw JSON → Feature Engineering → Scoring Model → Analysis
## Steps:
### 1.Preprocessing:
• Convert JSON to DataFrame

•	Timestamp parsing and sorting

•	Map action types

### 2.Feature Engineering:
•	Action frequencies

•	Ratios: repay-to-borrow, redeem-to-deposit

•	Time gaps between transactions

•	Liquidation count

•	Bot-like behavior (e.g., same-timestamp actions)

### 3.Scoring Model:
•	Weighted scoring using normalized features

•	Output range: 0 (high risk) to 1000 (trustworthy)

### 4.Categorical Analysis:
•	Score bins: [0-100], [100-200], …, [900-1000]

•	Plotting and interpretation

# Credit Score Logic
Credit Score =

     + High deposit + redeem activity
     
     – Liquidations
     
     – Bot-like behavior
     
     + Consistent repayment patterns
     
     + Healthy time gaps between actions
