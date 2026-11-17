<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/sigil-dark.svg">
  <img src="assets/sigil.svg" width="64" alt="Sohan Hajra sigil">
</picture>

# Sohan Hajra

### Quantitative Research · Research Engineering · Systematic Trading

I build research systems that make **assumptions, data quality, transaction costs, out-of-sample behavior, and failure modes** visible, not just the headline result.

[![Portfolio](https://img.shields.io/badge/Portfolio-sohanhajra.github.io-7b2b23?style=for-the-badge&logo=githubpages&logoColor=white)](https://sohanhajra.github.io/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sohan_Hajra-1d1c1a?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohan-hajra/)
[![Email](https://img.shields.io/badge/Email-sohancollege27%40gmail.com-1d1c1a?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sohancollege27@gmail.com)

**UIUC B.S. Mathematics & Computer Science · ACM SIGAI Author · UAE Golden Visa**

<sub>The <a href="https://sohanhajra.github.io/">portfolio</a> tells the story. This page indexes the evidence: repositories, numbers, and code.</sub>

</div>

---

## Now · Proposals Lab

[![Repository](https://img.shields.io/badge/View_repository-Proposals-7b2b23?style=flat-square&logo=github)](https://github.com/sohanHajra/Proposals)
![Method](https://img.shields.io/badge/Method-pre--registered-1d1c1a?style=flat-square)

A research-proposal series. Each question goes from a one-page proposal to running code. Hypotheses are written down before results, dead ends stay in the log, and null results get published.

| # | Proposal | Question | Status |
|---|---|---|---|
| 01 | [**From Signal to Fill**](https://github.com/sohanHajra/Proposals/tree/main/01-signal-to-fill) | When market conditions are matched, does extra delay between a trading decision and its order's outcome cost price or fills? I am currently replaying the same decision moments at controlled delays on public Binance BTCUSDT data. | In progress · release planned Nov 22, 2026 |

[Proposal](https://github.com/sohanHajra/Proposals/blob/main/01-signal-to-fill/PROPOSAL.md) · [Lab notebook](https://github.com/sohanHajra/Proposals/blob/main/01-signal-to-fill/LAB_NOTEBOOK.md) · [All posts on the Writing tab](https://sohanhajra.github.io/#writing)

---

## Selected work

### 01 · Nasdaq Closing Auction Forecasting

[![Repository](https://img.shields.io/badge/View_repository-Nasdaq_Auction_Research-1d1c1a?style=flat-square&logo=github)](https://github.com/sohanHajra/nasdaq-closing-auction-research)
[![Overview](https://img.shields.io/badge/Research_overview-portfolio-7b2b23?style=flat-square)](https://sohanhajra.github.io/research/nasdaq.html)
![Python](https://img.shields.io/badge/Python-1d1c1a?style=flat-square&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-1d1c1a?style=flat-square)

**Question:** can information available before the close improve forecasts of the final closing-cross price, without leaking future auction information?

| Fixed horizons | Model families | Final test set |
|---:|---:|---:|
| 6 | 3 | Frozen |

<details>
<summary><b>Research design</b></summary>
<br>

- Built stock-day targets and fixed-horizon features around indicative prices, signed imbalance, paired volume, and quoted liquidity, with leakage-safe timing.
- Compared market-price baselines, OLS/Ridge, and XGBoost.
- Used chronological train / validation / test splits rather than random cross-validation.
- Selected horizon-specific models on validation MAE and audited held-out robustness by trading date and error tail.

The part I care about most is not whether a more complicated model wins. It is whether the result survives a research design that makes it hard to fool myself.

</details>

---

### 02 · Systematic Trading Research Platform

[![Repository](https://img.shields.io/badge/View_repository-Systematic_Trading_Platform-1d1c1a?style=flat-square&logo=github)](https://github.com/sohanHajra/quant_trading_system)
[![Overview](https://img.shields.io/badge/Research_overview-portfolio-7b2b23?style=flat-square)](https://sohanhajra.github.io/research/systematic-trading.html)
![Python](https://img.shields.io/badge/Python-1d1c1a?style=flat-square&logo=python&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-1d1c1a?style=flat-square&logo=duckdb&logoColor=white)

**Question:** what survives when parameter choice, costs, warm-up history, and out-of-sample accounting are kept separate?

12-month training / 3-month out-of-sample walk-forward evaluation, 15 OOS folds, 5 bps turnover costs, benchmark comparison, and trade and regime attribution.

| OOS trades | CAGR | Annualized Sharpe | Max drawdown | Market exposure |
|---:|---:|---:|---:|---:|
| 22 | 9.18% | 0.82 | -11.79% | 75.77% |

<details>
<summary><b>What made this project useful</b></summary>
<br>

The baseline **reduced drawdown but did not beat SPY buy-and-hold on return or Sharpe**. That made the project more useful, not less.

I added trade-, regime-, portfolio-, and flat-period attribution to understand where the strategy helped, where it failed, and whether implementation mistakes were changing the result. I also reworked fold accounting so indicator warm-up history was separated from out-of-sample scoring, and positions, costs, trades, and compounded equity were recomputed only after each test boundary.

> Research baseline only. These are not live, audited, or client investment results.

</details>

---

### 03 · USO–WTI ETF/Futures Arbitrage · UIUC team project

[![Repository](https://img.shields.io/badge/View_repository-USO%2FWTI_Arbitrage-1d1c1a?style=flat-square&logo=github)](https://github.com/sohanHajra/USO-WTI_ETF-Futures_Arbitrage-FIN_556)
[![Overview](https://img.shields.io/badge/Project_overview-portfolio-7b2b23?style=flat-square)](https://sohanhajra.github.io/research/uso-wti.html)
![C++](https://img.shields.io/badge/C++-1d1c1a?style=flat-square&logo=cplusplus&logoColor=white)
![Markets](https://img.shields.io/badge/Data-IEX_%7C_NASDAQ_%7C_CME-1d1c1a?style=flat-square)

**Question:** how does a simple fair-value dislocation idea change once venue selection, inventory, order sizing, and working-order safety become real constraints?

<details>
<summary><b>My contribution</b></summary>
<br>

- Used CME crude-oil futures as a configurable fair-value proxy for USO.
- Routed threshold-triggered orders to the best available IEX/NASDAQ quote.
- Added inventory-skewed fair value, runtime-tunable thresholds and aggressiveness, position-aware sizing and limit pricing, working-order guards, and exit-to-flat logic.

This project pushed me from thinking about a signal in isolation to thinking about what happens **after** a signal exists: quoting, inventory, routing, order state, and risk.

</details>

---

## Publication

### An N-Gram Framework for Sentiment and Emotion-Aware Word Association Games

[![DOI](https://img.shields.io/badge/ACM_SIGAI_AI_Matters-10.1145%2F3774399.3774407-7b2b23?style=flat-square)](https://doi.org/10.1145/3774399.3774407)

Undergraduate research with a multidisciplinary Penn State team, combining n-gram co-occurrence and GloVe embeddings with VADER sentiment and SenticNet emotion labels. Published in **ACM SIGAI AI Matters 11(1), 49–58 (2025)**. I contributed model development, RMSE-based evaluation, analysis, and technical writing.

---

## Workbench

[**How much should you bet on an edge?**](https://sohanhajra.github.io/#workbench) An interactive Kelly bankroll simulator: drag the win probability, payout, and bet size, and watch 20 bankrolls compound on a log scale against the expected-growth curve g(f).

---

<details>
<summary><b>Earlier builds, revisited</b> · kept secondary to the research</summary>
<br>

**[Quizzo](https://github.com/sohanHajra/Quizzo)** · AI / product engineering · 2024, revisited 2026
A personal LLM quiz builder, prompted by generic questions not matching my own notes before exams. PDFs are chunked and embedded with Vertex AI, context is retrieved from Chroma, and Gemini writes structured multiple-choice questions. The 2026 pass revisits validation, state, retries, configuration, and tests. An early learning prototype, not a production service.

**[ChainDEX](https://github.com/sohanHajra/ChainDEX)** · Crypto / DeFi systems · 2023, revisited 2026
An educational DEX prototype exploring AMM liquidity pools and on-chain execution: a React interface around Uniswap V2-style router, factory, pair, and ERC-20 contracts, with swap quoting, approvals, minimum-output protection, and transaction-state handling. The revisit fixed a pair-filtering bug and documented limits around decimals, single-hop routing, and security. Not a production exchange or audited contract.

</details>

---

## Experience snapshot

| Experience | What I worked on |
|---|---|
| **Spade Labs · Data Engineering Intern** | Dockerized market-research pipeline on AWS SageMaker; PostgreSQL/pgvector ingestion across 1M+ embedding records |
| **Folio · Data Analyst Intern** | Python ETL, Airflow, SQLAlchemy, schema-change checks, DAG tests, retry handling |
| **RadicalX · AI Engineering Intern** | Containerized Python AI services, API integrations, prompt evaluation, MLflow and Prometheus |
| **Penn State · Undergraduate Student Researcher** | NLP model development, evaluation, analysis, and technical writing leading to the ACM SIGAI publication |

Full CV on the [portfolio](https://sohanhajra.github.io/#cv).

---

## Technical toolkit

**Languages:** `Python` `C++` `SQL` `C` `JavaScript`  
**Data & modeling:** `Pandas` `NumPy` `scikit-learn` `PyTorch` `XGBoost` `DuckDB` `PostgreSQL`  
**Infrastructure:** `Git/GitHub` `Docker` `AWS` `Linux/Bash` `Jupyter` `Airflow` `Databento` `REST APIs` `ethers.js` `Web3.js`

---

<details>
<summary><b>How I approach research</b></summary>
<br>

1. **Separate selection from evaluation.** Training and validation data make the choices; the final test set stays out of the decision loop.
2. **Benchmark before celebrating.** A result matters only against a credible baseline, realistic costs, and the risk it takes.
3. **Explain the miss.** When a result disappoints, attribution and failure analysis teach more than another parameter sweep.
4. **Write the hypothesis down first.** Pre-register, then test; publish the null results too.

</details>

---

## Currently

- Running Proposals Lab: one falsifiable market-microstructure or execution question at a time.
- Revisiting older projects with the standards I use today.
- Looking for early-career work where quantitative research, software, and market decision-making meet.

---

<div align="center">

[Portfolio](https://sohanhajra.github.io/) · [LinkedIn](https://www.linkedin.com/in/sohan-hajra/) · [Email](mailto:sohancollege27@gmail.com)

<sub>Projects here are meant to be read, questioned, and inspected.</sub>

</div>
