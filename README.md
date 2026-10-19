# Mini-Project 2: Solar Micro-Grid Dispatch Planner
**Context:** Rural Health Center Dispatch Planning in Kasese, Uganda  
**Course/Project:** MSDS Object-Oriented Python & Linear Algebra  

---

## 📂 Project Structure
```text
│
├── data/
│   └── microgrid_demand_30days.csv  # Generated 30-day demand dataset
├── src/
│   ├── __init__.py
│   ├── microgrid.py                 # Base class: 2x2 system, determinant, condition number
│   ├── data_generator.py            # Synthetic data generation with reproducible seeds
│   ├── dispatch_planner.py          # Task 3-7: Batch solving, vectorization, cost model, stats
│   └── hybrid_microgrid.py          # Extension: 3x3 hybrid model, linear dependence, Monte Carlo
├── venv/                            # Python virtual environment
└── README.md
### Findings
The 24-hour microgrid dispatch simulation reveals critical operational dynamics for off-grid energy management in rural Uganda. The results confirm that integrating a battery energy storage system (BESS) alongside solar PV eliminates midday curtailment while seamlessly shifting clean energy to cover the high-demand evening peak. By prioritizing battery discharge over immediate diesel activation, the system achieves significant cost savings and reduces carbon emissions. However, the model highlights a sharp economic tipping point: without sufficient storage capacity, evening demand spikes rapidly outstrip battery reserves, forcing heavy reliance on expensive auxiliary diesel generation. Furthermore, the simulation underscores that round-trip efficiency losses in lead-acid or lithium-ion batteries must be carefully accounted for, as inefficient storage can silently erode up to 15% of captured solar yield. These insights provide microgrid operators with a quantitative basis for sizing storage assets relative to local community consumption profiles.
#### Limitations
Despite its robust optimization logic, the model relies on several simplifying assumptions. First, the simulation operates on deterministic 24-hour profiles and does not account for stochastic weather disruptions, such as sudden cloud cover or heavy rainy-season storms that can drastically depress solar generation for multiple consecutive hours. Second, the battery degradation model assumes a constant efficiency rate and ignores thermal stress, depth-of-discharge aging curves, and capacity fade over multi-year operational horizons. Finally, the economic cost function treats diesel fuel pricing as static, ignoring regional transport premiums and macroeconomic exchange rate volatility. Future enhancements should incorporate stochastic solar irradiance modeling via Markov chains and dynamic load-shifting incentives.
