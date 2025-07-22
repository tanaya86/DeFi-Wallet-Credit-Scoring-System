# Wallet Score Analysis

| Score Range | % of Wallets | Characteristics |
|-------------|--------------|------------------|
| 300-400 | 12% | High volatility, mostly redeem actions, short activity bursts |
| 400-500 | 18% | Moderate volume, unbalanced action ratios |
| 500-600 | 25% | Some stablecoin usage, irregular activity |
| 600-700 | 30% | Consistent deposits, multiple assets |
| 700-850 | 15% | High volume, long activity history, balanced ratios |

## High-Score Wallets (700-850)
**Top 5 Characteristics:**
1. **Total Volume**: $250k+ USD equivalent
2. **Activity Duration**: 60+ days
3. **Asset Diversity**: 3+ asset types
4. **Stablecoin Ratio**: >40% of transactions
5. **Deposit/Repay Ratio**: >65% of actions

**Example Wallet:**  
`0x000...3852c`  
- Score: 812  
- Total Volume: $1.2M  
- Days Active: 142  
- Assets: USDC, WETH, WBTC  
- Deposit Ratio: 72%

## Low-Score Wallets (300-400)
**Common Patterns:**
1. **Transaction Patterns**:
   - Short bursts of activity (1-3 days)
   - High redeem/borrow ratios (>80%)
   - Extreme transaction size variation

2. **Asset Concentration**:
   - 92% focus on single asset class
   - Minimal stablecoin usage

3. **Behavioral Red Flags**:
   - Rapid large borrows followed by redeems
   - No repay history
   - High volume volatility (std/mean > 2.5)

**Example Wallet:**  
`0x000...e2dc`  
- Score: 327  
- Total Volume: $18k  
- Days Active: 2  
- Actions: 4 redeems, 1 borrow  
- Asset: 100% WMATIC

## Key Insights
1. **Score Drivers**:
   - Long-term consistency boosts scores more than one-time large deposits
   - Stablecoin usage correlates strongly with higher scores
   - Even small repay activity significantly improves scores

2. **Anomaly Detection**:
   - 8% of wallets showed "hit-and-run" patterns (single day activity)
   - 15% of low-score wallets had suspiciously repeating transaction amounts

3. **Protocol Health**:
   - Top 20% of wallets account for 78% of total protocol volume
   - Healthy distribution with majority (55%) in medium-risk ranges

The analysis shows the system effectively differentiates between:
- **Responsible users**: Long-term, diversified, stablecoin-heavy
- **Risky behavior**: Short-term, volatile, redeem-focused
- **Potential bots**: Extremely frequent, patterned transactions

The score distribution follows expected patterns with most wallets in the medium range and clear differentiation at extremes.
