
#  Wallet Credit Score Analysis

This document summarizes the analysis of credit scores assigned to wallets based on Aave V2 transaction data. The model scored each wallet between **0 to 1000**, reflecting reliability, repayment habits, and transactional patterns.

---

##  Score Distribution

Wallets were categorized into the following score brackets:

| Category   | Score Range | Description                       |
|------------|-------------|-----------------------------------|
| Excellent  | 800–1000    | Highly reliable and responsible   |
| Good       | 600–799     | Generally responsible, few risks  |
| Fair       | 400–599     | Average behavior, moderate risk   |
| Risky      | 0–399       | High-risk or suspicious patterns  |

![Wallet Credit Score Distribution]
<img width="790" height="490" alt="output" src="https://github.com/user-attachments/assets/394bc370-be4f-42a6-8d8e-3cb0b26f1e09" />

---

##  Category-wise Behavior Analysis

### Excellent (800–1000)
- **Largest group** (~2,400+ wallets).
- High deposit-to-borrow ratio.
- Very low or no liquidation events.
- Consistent and timely repayments.
- Fewer interactions, suggesting long-term holders or responsible usage.

### Good (600–799)
- Moderate deposit/repay patterns.
- Rare but present liquidation or late repayments.
- Likely retail users with normal usage habits.
- Some bot indicators like regular interval transactions.

### Fair (400–599)
- Unstable behavior with mixed transaction types.
- Medium frequency of repayments or redemptions.
- More borrow-heavy behavior than deposits.
- Includes new or infrequent users.

### Risky (0–399)
- Lowest-scoring group (smallest subset).
- Frequently involved in **liquidation events**.
- Irregular patterns, fast interactions across assets.
- Clear signs of bot-like or exploitative behavior (e.g., flash loans, repetitive cycles).
- Often borrow without repaying or redeeming too soon.

---

##  Insights

- Majority of wallets fall into **Excellent**, indicating high reliability among users.
- Only a small subset is **Risky**, but these pose the greatest threat to protocol health.
- The credit scoring system could help DeFi lenders apply dynamic interest rates or collateral requirements.
- Wallet behavior shows that on-chain transaction history is a **powerful proxy** for user risk assessment.
