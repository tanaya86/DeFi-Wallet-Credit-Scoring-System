# DeFi-Wallet-Credit-Scoring-System

## Overview
This system assigns credit scores (300-850) to cryptocurrency wallets based on their transaction behavior in Aave V2 protocol. The scores reflect wallet reliability, with higher scores indicating more responsible usage patterns.

## Methodology

### Feature Engineering
We extract 18 features from raw transaction data:
- **Activity Metrics**: Total transactions, unique assets, transaction frequency
- **Financial Patterns**: Transaction amounts (avg, std, sum, max), volume volatility
- **Behavioral Ratios**: Deposit/borrow/repay/redeem ratios
- **Asset Allocation**: Stablecoin/crypto/native asset ratios
- **Temporal Features**: Days active, recency, active days ratio

### Model Architecture
- **Algorithm**: Random Forest Regressor (200 trees, max depth 10)
- **Preprocessing**: Standard scaling of numeric features
- **Validation**: 80/20 train-test split with RMSE evaluation
- **Synthetic Training**: Realistic score simulation based on feature importance

### Processing Flow
1. **Data Ingestion**: Load raw JSON transaction data
2. **Feature Extraction**:
   - Calculate USD values for all transactions
   - Compute time-based metrics
   - Derive behavioral ratios
3. **Model Training**:
   - Preprocess features
   - Train Random Forest on synthetic labels
   - Validate performance
4. **Scoring**:
   - Generate predictions for each wallet
   - Scale scores to 300-850 range
5. **Output**: Wallet addresses with scores and key metrics

## Key Assumptions
1. Stablecoin usage indicates lower risk
2. Consistent activity over time is positive
3. High volatility in transaction amounts is risky
4. Balanced deposit/borrow ratios are favorable

## Extensibility
To adapt this system:
1. Replace synthetic labels with real default data
2. Add more protocols for comprehensive coverage
3. Incorporate on-chain reputation systems
4. Add time-decay factors for older transactions
