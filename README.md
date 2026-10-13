<div align="center">

# Sohan Hajra

### Quantitative Research · Research Engineering · Systematic Trading

I build research systems that make **assumptions, data quality, transaction costs, out-of-sample behavior, and failure modes** visible - not just the headline result.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sohan_Hajra-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohan-hajra/)
[![Email](https://img.shields.io/badge/Email-sohancollege27%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sohancollege27@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-sohanHajra-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sohanHajra)
[![Portfolio](https://img.shields.io/badge/Portfolio-sohanhajra.github.io-0F766E?style=for-the-badge&logo=githubpages&logoColor=white)](https://sohanhajra.github.io/)

**UIUC B.S. Mathematics & Computer Science · GPA 3.49 / 4.00 · ACM SIGAI Author · UAE Golden Visa**

</div>

---

## Portfolio map

| Research question | What I built | What it demonstrates |
|---|---|---|
| Can closing-auction information improve short-horizon price forecasts without leakage? | **Nasdaq Closing Auction Forecasting Research** | Market microstructure, feature design, chronological validation, model comparison |
| Does a simple systematic signal survive costs and unseen market regimes? | **Systematic Trading Research Platform** | Walk-forward research, backtesting discipline, attribution, debugging |
| How does a DEX actually discover liquidity and execute a token swap on-chain? | **ChainDEX** | AMMs, liquidity pools, contract interaction, execution mechanics |
| How can ETF/futures dislocations be translated into executable trading logic? | **USO/WTI ETF-Futures Arbitrage** | C++, execution logic, fair value, inventory-aware risk controls |

> **How to use this portfolio:** start with the project that matches your interest, then expand the sections below for the research question, implementation choices, and what I learned.

---

## Featured research & projects

### 1. Nasdaq Closing Auction Forecasting Research

[![Repository](https://img.shields.io/badge/View_repository-Nasdaq_Auction_Research-181717?style=flat-square&logo=github)](https://github.com/sohanHajra/nasdaq-closing-auction-research)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-modeling-1F425F?style=flat-square)

Short-horizon research around the Nasdaq closing auction using indicative auction prices, signed imbalance, paired volume, and quoted liquidity.

<details>
<summary><b>Research design</b></summary>
<br>

- Built stock-day targets and fixed-horizon features with leakage-safe timing.
- Compared market-price baselines, OLS/Ridge, and XGBoost.
- Used chronological train / validation / test splits rather than random cross-validation.
- Selected horizon-specific models on validation MAE and audited held-out robustness by trading date and error tail.

The part I care about most is not whether a more complicated model wins — it is whether the result survives a research design that makes it hard to fool myself.

</details>

---

### 2. Systematic Trading Research Platform

[![Repository](https://img.shields.io/badge/View_repository-Systematic_Trading_Platform-181717?style=flat-square&logo=github)](https://github.com/sohanHajra/quant_trading_system)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?style=flat-square&logo=duckdb&logoColor=000000)
![Research](https://img.shields.io/badge/Focus-Walk--forward_validation-4C78A8?style=flat-square)

An independent research platform for testing equity strategies with explicit transaction costs, rolling out-of-sample evaluation, benchmark comparison, and attribution.

| OOS trades | CAGR | Annualized Sharpe | Max drawdown | Market exposure |
|---:|---:|---:|---:|---:|
| 22 | 9.18% | 0.82 | -11.79% | 75.77% |

<details>
<summary><b>What made this project useful</b></summary>
<br>

The strategy **did not beat SPY buy-and-hold on return or Sharpe** during the evaluated period. That made the project more useful, not less.

I added trade-, regime-, portfolio-, and flat-period attribution to understand where the strategy helped, where it failed, and whether implementation mistakes were changing the result. I also reworked fold accounting so indicator warm-up history was separated from out-of-sample scoring and positions, costs, trades, and compounded equity were recomputed only after each test boundary.

> Research baseline only. These are not live, audited, or client investment results.

</details>

---

### 3. ChainDEX — Ethereum DEX Prototype

[![Repository](https://img.shields.io/badge/View_repository-ChainDEX-181717?style=flat-square&logo=github)](https://github.com/sohanHajra/ChainDEX)
![Ethereum](https://img.shields.io/badge/Ethereum-3C3C3D?style=flat-square&logo=ethereum&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Web3.js](https://img.shields.io/badge/Web3.js-F16822?style=flat-square&logo=web3dotjs&logoColor=white)

One of my earlier market-technology projects. I built a wallet-connected decentralized-exchange prototype to understand **AMMs, liquidity pools, approvals, routing, and on-chain execution** beyond the surface-level idea of “crypto trading.”

<details>
<summary><b>Under the hood</b></summary>
<br>

The application follows a Uniswap V2-style contract hierarchy:

```text
wallet → router → factory → pair contracts → token metadata / liquidity
             ↘ quote → approval → minimum-output guard → swap
```

It discovers pools from contract state, reads ERC-20 balances and allowances, quotes swaps with `getAmountsOut`, handles approvals, and submits token swaps. When I revisited the project, I also fixed a pair-filtering bug, added minimum-output slippage protection, and documented limitations around token decimals, single-hop routing, historical Goerli infrastructure, and production security.

What I like about revisiting old projects is that they show two things at once: what I knew when I built them, and how much more critically I can evaluate them now.

</details>

---

### 4. USO/WTI ETF-Futures Arbitrage — C++ Team Project

[![Repository](https://img.shields.io/badge/View_repository-USO%2FWTI_Arbitrage-181717?style=flat-square&logo=github)](https://github.com/sohanHajra/USO-WTI_ETF-Futures_Arbitrage-FIN_556)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Markets](https://img.shields.io/badge/Data-IEX_%7C_NASDAQ_%7C_CME-0B3D91?style=flat-square)

A UIUC team project translating ETF/futures dislocations into executable trading logic in TT Strategy Studio.

<details>
<summary><b>My contribution</b></summary>
<br>

- Used CME crude-oil futures as a configurable fair-value proxy for USO.
- Routed threshold-triggered orders to the best available IEX/NASDAQ quote.
- Added inventory-skewed fair value, runtime-tunable thresholds and aggressiveness, position-aware sizing and limit pricing, working-order guards, and exit-to-flat logic.

This project pushed me from thinking about a signal in isolation to thinking about what happens **after** a signal exists: quoting, inventory, routing, order state, and risk.

</details>

---

## Research publication

### An N-Gram Framework for Sentiment and Emotion-Aware Word Association Games

[![DOI](https://img.shields.io/badge/ACM_SIGAI_AI_Matters-10.1145%2F3774399.3774407-0085CA?style=flat-square)](https://doi.org/10.1145/3774399.3774407)

Co-authored research combining n-gram co-occurrence and GloVe embeddings with VADER sentiment scores and SenticNet emotion labels. Published in **ACM SIGAI AI Matters 11(1), 49–58 (2025)**.

---

## Experience snapshot

| Experience | What I worked on |
|---|---|
| **Spade Labs — Data Engineering Intern** | Dockerized market-research pipeline on AWS SageMaker; PostgreSQL/pgvector ingestion across 1M+ embedding records |
| **Folio — Data Analyst Intern** | Python ETL, Airflow, SQLAlchemy, schema-change checks, DAG tests, retry handling |
| **RadicalX — AI Engineering Intern** | Containerized Python AI services, API integrations, prompt evaluation, MLflow and Prometheus |
| **Penn State — Undergraduate Student Researcher** | NLP model development, evaluation, analysis, and technical writing leading to the ACM SIGAI publication |

---

## Technical toolkit

**Languages & data**  
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

`Pandas` `NumPy` `scikit-learn` `PyTorch` `XGBoost` `DuckDB` `PostgreSQL`

**Engineering & research infrastructure**  
`Git/GitHub` `Docker` `AWS` `Linux/Bash` `Jupyter` `Airflow` `Matplotlib` `Databento` `REST APIs` `ethers.js` `Web3.js`

---

## How I approach research

```text
question
  ↓
define the benchmark
  ↓
build the smallest defensible experiment
  ↓
separate training information from evaluation
  ↓
model costs + implementation constraints
  ↓
look for the failure mode
  ↓
only then decide whether the result is interesting
```

<details>
<summary><b>Five principles I try to follow</b></summary>
<br>

1. **Define the hypothesis and benchmark before tuning.**
2. **Keep training history separate from out-of-sample scoring.**
3. **Model costs, exposure, turnover, and implementation constraints.**
4. **Treat implementation details as part of the research result.**
5. **Report errors, limitations, and underperformance — not only the good-looking number.**

</details>

---

## Currently

- Deepening my work in **market microstructure, systematic research, and research engineering**.
- Revisiting older projects with the standards I use today — ChainDEX is one example.
- Looking for new-graduate opportunities where research, statistics, software, and markets meet.

---

<div align="center">

### Want to talk research, markets, or engineering?

[Portfolio](https://sohanhajra.github.io/) · [LinkedIn](https://www.linkedin.com/in/sohan-hajra/) · [Email](mailto:sohancollege27@gmail.com) · [GitHub](https://github.com/sohanHajra)

<sub>Built as the front page of my technical portfolio - projects above are intended to be read, questioned, and inspected.</sub>

</div>
