# Sohan Hajra

**Quantitative Research · Research Engineering · Systematic Trading**

Mathematics & Computer Science graduate from the University of Illinois Urbana-Champaign (**GPA: 3.49 / 4.00**). I like building research systems that make assumptions, data quality, transaction costs, out-of-sample behavior, and failure modes inspectable rather than hiding them behind headline results.

I am targeting new-graduate roles across quantitative research, research engineering, quantitative development, systematic trading, and adjacent trading technology. I am open to the United States, UK/Europe, APAC, and the UAE; I hold a UAE Golden Visa.

## Current research

### Nasdaq Closing Auction Forecasting Research

Independent research on short-horizon price behavior around the Nasdaq closing auction.

- Built leakage-safe stock-day targets and fixed-horizon features from indicative auction prices, signed imbalance, paired volume, and quoted liquidity.
- Compared market-price baselines, OLS/Ridge, and XGBoost using chronological train / validation / test splits.
- Selected horizon-specific models on validation MAE and audited held-out robustness by date and error tail.

### Systematic Trading Research Platform

Independent Python platform for testing equity strategies with explicit data validation, transaction costs, walk-forward evaluation, and attribution.

- Built an OHLCV pipeline with DuckDB storage, parameter sweeps, and rolling 12-month training / 3-month out-of-sample evaluation.
- Evaluated a SPY long/flat trend baseline across 15 out-of-sample folds at 5 bps transaction costs.
- Added trade, regime, portfolio, and flat-period attribution to explain return drivers and benchmark shortfalls.
- Corrected warm-up and fold-accounting errors by isolating indicator history from out-of-sample scoring and recomputing positions, costs, trades, and compounded equity after each test boundary.

| OOS trades | CAGR | Sharpe | Maximum drawdown | Market exposure |
|---:|---:|---:|---:|---:|
| 22 | 9.18% | 0.82 | -11.79% | 75.77% |

> Research baseline only. These are not live, audited, or client investment results. The strategy underperformed SPY buy-and-hold on return and Sharpe during the evaluated period.

## Selected work

### ChainDEX — Ethereum DEX prototype

Built a wallet-connected decentralized-exchange prototype to understand AMM and on-chain execution mechanics directly. The application uses Uniswap V2-style router, factory, pair, and ERC-20 interfaces to discover liquidity pools, quote swaps, manage approvals, and submit token swaps. Revisiting the project later also led me to add a minimum-output slippage guard and document production limitations explicitly.

### USO/WTI ETF-Futures Arbitrage — C++ team project

Co-developed a C++ trading strategy using CME crude-oil futures as a fair-value proxy for USO, with best-venue routing across IEX/NASDAQ, inventory-aware fair-value adjustments, position-sensitive sizing, working-order guards, and exit-to-flat logic.

### Published NLP research

Co-authored [“An N-Gram Framework for Sentiment and Emotion-Aware Word Association Games”](https://doi.org/10.1145/3774399.3774407), *ACM SIGAI AI Matters* 11(1), 49–58 (2025).

## Research and engineering experience

- **Spade Labs — Data Engineering Intern:** built a Dockerized market-research pipeline on AWS SageMaker and a PostgreSQL/pgvector ingestion workflow for embedding data.
- **Folio — Data Analyst Intern:** built Python ETL pipelines and added schema checks, Airflow DAG tests, and retry handling.
- **RadicalX — AI Engineering Intern:** developed containerized Python AI services, API integrations, prompt-evaluation workflows, and MLflow/Prometheus experiment logging.
- **Penn State University — Undergraduate Student Researcher:** contributed to sentiment- and emotion-aware word-association research that led to the ACM SIGAI publication.

## Technical focus

`Python` `C++` `SQL` `C` `Pandas` `NumPy` `scikit-learn` `PyTorch` `XGBoost` `DuckDB` `PostgreSQL` `Docker` `AWS` `Linux/Bash` `Git` `ethers.js` `Web3.js`

## Research principles

- Define the hypothesis and benchmark before tuning.
- Keep training history separate from out-of-sample scoring.
- Model costs, exposure, turnover, and implementation constraints.
- Treat implementation details as part of the research result.
- Report errors, limitations, and underperformance, not only headline metrics.

## Contact

[LinkedIn](https://www.linkedin.com/in/sohan-hajra/) · [Email](mailto:sohancollege27@gmail.com)
