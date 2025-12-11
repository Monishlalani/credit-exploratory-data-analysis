# credit-exploratory-data-analysis


Applying EDA to understand  risk analytics in banking and financial services and understand how data is used to minimise the risk of losing money while lending to customers.


[![MATPLOTLIB](https://img.shields.io/badge/-MATPLOTLIB-007aa6?style=for-the-badge)](https://img.shields.io/badge/-MATPLOTLIB-007aa6?style=for-the-badge) [![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue) [![Jupyter](https://img.shields.io/badge/-Jupyter-f5841f?style=for-the-badge)](https://img.shields.io/badge/-Jupyter-f5841f?style=for-the-badge) [![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white) [![Numpy](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white)](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white) <a href="https://www.microsoft.com/en-in/microsoft-365/excel" rel="nofollow"><img alt="Excel" src="https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" data-canonical-src="https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" style="max-width: 100%;"/></a>

## Visualization

### Clients income amount vs education (Target 0 are non defaulter & Target 1 are defaulter).
[![Architecure Diagram](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182550.png?raw=true)](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182550.png?raw=true)
- Based on there avgerage income of different occupation we can provide loan to the new clients as per as there income and occupation.



### Clients income amount vs income type based on family status (Target 0 are non defaulter & Target 1 are defaulter).
[![Architecure Diagram](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182720.png?raw=true)](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182720.png?raw=true)
- Business man and commercial associate are likely to apply more for loan and are Non-defaulters
- Married Business man have more income compared to others and are non defaulters.
- While pensioner, student and unemployed have high risk of defaulters due to low income.


## Final conclusion
- Person with Higher education , Academic degree should be preferred.
- Applicant with income type of Business and commercial associate are likely to be non default.
- Person with House as an asset can be preferred as a asset collateral and can we given loan.
- Based on there avgerage income of different occupation we can provide loan to the new clients as per as there income and occupation.
- Applicants who are employed and are married have lesser chance to be defaulter.
- Male clients with Incomplete Education having very low salaries have a high risk of default.
- 30% of people of loan purpose Refusal to name the goal were defaulters.
- Hobby,Money for a third person,Payments on other loans,Gasification / water supply ,Car repairs may have high chance to be defaulters
- 9.57% people with income type Unemployed have high chance to be defaulters.


## Author

Monish Lalani

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/monish-lalani/) 
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:monishlalani12@gmail.com)  




In Television Audience Measurement (TAM) the path a newly‑installed meter takes before its data appear in the final audience‑report is a series of discrete steps:

1. *Meter shipped → field‑team receives*
2. *Field‑team schedules installation*
3. *Installation performed*
4. *Meter data transmitted to the data‑center*
5. *Data cleaned and validated*
6. *Data aggregated into the production database*
7. *Inclusion in the published report (final state)*

Each step can be modelled as a state of a discrete‑time (or continuous‑time) Markov chain.  The “waiting time” we want is the time from the first state (shipment) to the absorbing state (report inclusion).  The Markov‑chain framework gives a direct way to compute the expected waiting time and its distribution, provided we can estimate the transition probabilities (or rates) between the states.

### Building the Markov model
1. *Define the state space* – a finite set that mirrors the workflow above, e.g.
`S = {0‑Shipped, 1‑Received, 2‑Scheduled, 3‑Installed, 4‑Data‑Received, 5‑Validated, 6‑Aggregated, 7‑Published}`.
State 7 is absorbing.

2. *Estimate transition probabilities* – from historical operational logs we can compute, for each state, how often the process moves to the next state, stays in the same state (delay), or moves back (e.g., a failed installation).  For a discrete‑time model the probabilities are simply the empirical frequencies of each outcome per day (or per reporting period).  For a continuous‑time model we fit exponential holding times to the observed dwell times in each state.

3. *Write the transition matrix \(P\)* – the matrix contains the probabilities \(p_{ij}\) of moving from state \(i\) to state \(j\).  The absorbing state has \(p_{77}=1\) and all other entries in that row zero.

4. *Set up the linear system for expected hitting times*
\[h_i = 1 + \sum_{j\neq 7} p_{ij}\,h_j ,\qquad i\neq7,\]
with \(h_7 = 0\).  In matrix form \(\mathbf{h} = (I - Q)^{-1}\mathbf{1}\), where \(Q\) is the sub‑matrix that excludes the absorbing row/column.

5. *Solve for \(\mathbf{h}\)* – the solution vector gives the expected number of steps (days, weeks, etc.) from each state to the final report.  The value \(h_0\) is the quantity we need: the average time from meter shipment to inclusion in production.

### What the model tells us
- *Baseline waiting time* – \(h_0\) is the mean lead‑time for a newly installed meter.  This is useful for planning the sample rotation and for contractual service‑level agreements.

- *Bottleneck identification* – the expected contribution of each state to the total waiting time can be read from the solution.  Large values for state 3 (installation) or state 5 (validation) highlight where operational improvements will have the biggest impact.

- *What‑if analysis* – by altering a single transition probability (e.g., increasing the probability that an installation succeeds on the first visit from 0.85 to 0.95) we can recompute \(\mathbf{h}\) and quantify the reduction in overall waiting time.

- *Variance and percentiles* – the Markov framework also yields higher moments.  The fundamental matrix \(N = (I - Q)^{-1}\) gives the variance of the hitting time: \(\text{Var}(\tau) = N(2\mathbf{h} - \mathbf{1}) - \mathbf{h}\odot\mathbf{h}\).  From this we can derive confidence intervals or the 90 % quantile, which are often more relevant for production scheduling than the mean alone.

### Practical steps for a TAM organization
1. *Log every transition* – each time a meter moves from “shipped” to “received”, from “installed” to “data received”, etc., record the timestamp and the outcome (success / failure / rework).  A simple relational table with columns `(meter_id, from_state, to_state, timestamp, outcome)` is sufficient.

2. *Fit the model* – aggregate the logs to obtain empirical transition counts per state and per time bucket.  Use these counts to estimate \(p_{ij}\) (or the exponential rates for a CTMC).

3. *Validate* – compare the model‑predicted distribution of total lead‑time with a hold‑out sample of meters.  If the fit is poor, refine the state granularity (e.g., split “validation” into “auto‑validation” and “manual‑review”) or use a higher‑order Markov chain that remembers the last outcome.

4. *Deploy* – embed the solver (or a pre‑computed lookup table of \(h_i\) values) into the operational dashboard.  As new meters are shipped, the system can instantly display the expected date they will appear in the audience report.

### Limitations to keep in mind
- *Markov property* – the assumption that the next step depends only on the current state may be violated if, for example, the probability of a failed installation depends on how many times the meter has already been visited.  In such cases a semi‑Markov or higher‑order model is needed.

- *State‑space explosion* – if the workflow has many parallel branches (different meter models, regional teams, etc.) the number of states can grow quickly.  Aggregation or hierarchical modelling helps keep the matrix tractable.

- *Data quality* – the accuracy of the waiting‑time estimate is only as good as the logged transition data.  Missing or mis‑coded events will bias the transition probabilities.

### Bottom line
By representing the end‑to‑end meter‑to‑production pipeline as a Markov chain, the TAM team can turn raw operational logs into a quantitative forecast of how long a new meter will take to become usable.  The expected hitting time \(h_0\) gives a single, interpretable metric, while the underlying linear equations reveal where delays originate and how changes to the process will affect overall lead‑time.  This principled, data‑driven approach replaces guesswork with a repeatable estimate that can be updated automatically as the measurement system evolves. ‎<This message was edited>







