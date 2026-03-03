# Crypto Carry and Term-Structure Arbitrage

A systematic relative-value strategy exploiting structural distortions in the crypto futures term structure.

This project documents the evolution of a live calendar-spread arbitrage strategy deployed across BTC and ETH futures during 2024–2025.

Full Research Paper (PDF): [Crypto Carry and Term-Structure Arbitrage](./Crypto Carry and Term-Structure Arbitrage.pdf)

---

## Overview

Crypto derivatives markets exhibit persistent structural contango driven by:

- Strong retail long bias   
- Limited institutional arbitrage capital  
- ETF-driven front-end futures demand  

These forces create chronically rich futures pricing and recurring term-structure distortions.

While traditional spot–futures basis trades capture this carry, this research focuses on a cleaner opportunity:

**Relative value mispricings between adjacent futures maturities.**

---

## Strategy Summary

Monthly crypto futures alternate between:

- 28-day maturity gaps (4 weeks)
- 35-day maturity gaps (5 weeks)

The 35-day spread should command ~25% more carry than the 28-day spread.

However, markets frequently priced both spreads at similar absolute dollar levels, violating basic time-value consistency.

### Trade Structure

When mispricing occurred:

- Long 4 × 35-day spreads  
- Short 5 × 28-day spreads  

This ratio:

35 / 28 ≈ 1.25

balances time exposure and isolates relative carry distortions while minimizing directional BTC/ETH exposure.

---

## Entry & Exit Logic

**Entry Conditions**
- Equal absolute spread pricing
- 2–3σ deviation from theoretical ratio
- Implied carry divergence

**Exit Conditions**
- Reversion to theoretical band
- Carry normalization
- Time decay realization
- Pre-expiry roll management

Typical holding period: several days to three weeks.

---

## Performance Snapshot

| Period | CAGR | Sharpe | t-stat | Max DD |
|--------|------|--------|--------|--------|
| Full 15 Months | 8% | 1.4 | 1.6 | -6.5% |
| Last 6 Months | 18% | 4.0 | 2.8 | -0.7% |

Characteristics:

- High frequency of small, repeatable gains  
- Low correlation to underlying crypto price  
- Lower volatility than outright futures  
- Capital efficient due to spread margining  

---

## Why the Opportunity Exists

- Retail activity concentrates in directional exposure  
- Perpetual swaps dominate attention  
- Adjacent maturities are often priced heuristically  
- Limited dedicated calendar arbitrage capital  

In short:

Retail leverage demand + structural contango + under-arbitraged term relationships = persistent relative value dislocations.

---

## Risk Profile

Primary risks include:

- Regime shift to backwardation  
- Liquidity stress events  
- Expiry-related distortions  
- Term-structure regime change  

Spread volatility was materially lower than outright futures, resulting in smoother P&L behavior relative to directional crypto exposure.

---

## Implementation

The research and monitoring framework was built in Python and includes:

- Futures market data ingestion  
- Spread construction and implied carry calculation  
- Statistical dislocation detection  
- Signal generation and monitoring  
- Semi-automated execution tracking  

Futures-only implementation enabled:

- No borrow constraints  
- Tight bid-ask spreads  
- Efficient margin usage  
- Straightforward scalability  

---

## Key Insights

- Term-structure relative value offers cleaner risk than spot basis trades  
- Small maturity differences can create large annualized carry discrepancies  
- Ratio relationships are more informative than absolute spread levels  
- Crypto derivatives remain structurally less efficient than traditional futures markets  

---

## Additional Materials

Full research write-up with methodology, statistical tests, and structural discussion:

→ [Download Full PDF](./Crypto Carry and Term-Structure Arbitrage.pdf)
