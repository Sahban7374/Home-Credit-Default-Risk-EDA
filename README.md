EXECUTIVE BRIEFING REPORT: CREDIT DEFAULT RISK ANALYSIS



Document Title: Credit Portfolio Audit & Risk Profiling Report

Target Audience: Chief Risk Officer (CRO) & Credit Policy Committee

Dataset Reference: Home Credit Default Risk Portfolio (307,511 Applicants)

 
1. Executive Summary      
          The primary objective of this audit is to dissect the risk profile of loan applicants before deploying predictive machine learning pipelines. By analyzing historical application data, credit bureau histories, and monthly payment tracking, this report establishes a data-driven baseline for the bank’s lending policy.
Our core finding reveals a baseline default rate of 8.07% across the historical portfolio. While a raw accuracy of 91.93% can be achieved by blindly approving all applicants, doing so poses an existential threat to the bank's capital. This report highlights critical risk hot-spots within youth demographics, lower educational tiers, and structural data anomalies that must be addressed to safeguard lending operations.

2. Data Portfolio & Structural Audit          
          We audited three primary relational data structures to build a comprehensive view of the customer.
Data Integrity & Volatility Summary:
•	Severe Class Imbalance: Out of 307,511 primary applicants, 282,686 are safe (repaid successfully), while 24,825 are high-risk (defaulted).
•	Information Gaps: External credit scoring metrics (EXT_SOURCE) contain up to 60% missing data in certain segments, creating dangerous blind spots for standard evaluation processes.

3. High-Risk Customer Profiling (Demographic Drivers)
          Our bivariate exploratory analysis identified two major institutional risk drivers:
A. The Youth Risk Premium (Age Dynamics)
Statistical distribution shows an aggressive concentration of defaults among younger applicants. Individuals aged between 20 and 35 years exhibit the highest density of default behavior. Risk steadily declines as the applicant matures, with older demographics displaying significantly more stable repayment patterns due to established career paths and financial maturity.
B. Educational Cushioning
There is a stark negative correlation between educational attainment and default probability:
•	Academic Degree Holders: Exhibit a minimal default rate of just 1.83%.
•	Lower Secondary Education Segment: Displays an alarming default rate of 10.92%. Lending to lower educational tiers without additional collateral introduces maximum volatility into the portfolio.
                 
4. Operational Anomalies & Outliers
          During the data audit, two critical anomalies were detected that require immediate administrative intervention before algorithmic processing:
•	The 1000-Year Employment Glitch: Exactly 55,374 applicants (18.01% of the dataset) have their employment duration recorded as exactly 365,243 days. This is an administrative placeholder representing unemployed or retired applicants. Treating this literally distorts risk metrics.
•	Extreme Wealth Outliers: While the average applicant's income stands at approximately 147,000, extreme outliers reach as high as 117 million. High-net-worth data compresses standard visualization scales and skew traditional scorecards.
 
5. Next-Generation Engineered Risk Indicators
         To capture complex financial stress, we generated 10 advanced financial metrics. The three most operationally significant metrics include:
Credit-to-Income Leverage Ratio: Measures total loan exposure against annual income. Historical trends indicate that when a loan amount exceeds 5x an applicant's verified annual income, default risk escalates exponentially.
Annuity-to-Income Debt Burden: Tracks the monthly cash-flow squeeze. If the monthly loan installment consumes more than 25-30% of the applicant's monthly income, the default probability spikes due to a lack of disposable income.
External Credit Score Aggregation (EXT_SOURCES_MEAN): Combining disparate external credit bureau scores into a single consolidated metric provides a multi-dimensional view of credit history, acting as our most reliable filter for fraudulent applications.

6. Strategic Policy Recommendations (Actionable Steps)
            Based on the empirical evidence from this data audit, the Credit Policy Committee is advised to implement the following changes:
Introducing Age-Based Credit Caps: Restrict initial credit limits by 20% for applicants under the age of 30. Allow automatic limit expansion only after a clean 6-month repayment track record.
Mandate Debt-Burden Thresholds: Enforce a hard cap preventing any loan approval where the monthly annuity exceeds 25% of the borrower’s verified net monthly income.
Isolate High-Net-Worth Scorecards: Bypass standard consumer scoring engines for applicants reporting an income over 1 Million. Route them to a specialized 'Premium Wealth Scorecard' pipeline involving manual asset verification.
Quarantine Missing-Score Applicants: Any applicant lacking all three external bureau scores should be automatically flagged for enhanced physical verification or rejected to avoid thin-file exposure.
