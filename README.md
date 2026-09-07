## Power-BI-Dashboard-Analysis-Bank-Marketing-Campaign-Data
This analysis uses the Bank Marketing Campaigns dataset (UCI / Kaggle, S. Moro, P. Cortez, P. Rita, 2014), which records the outcomes of a Portuguese bank's direct-call term-deposit campaign. The dataset contains 41,188 client records across 21 variables, including client demographics. The dataset is complete, with no missing values. 

## 1. Dataset Selected
This analysis uses the Bank Marketing Campaigns dataset (UCI / Kaggle, S. Moro, P. Cortez, P. Rita, 2014), which records the outcomes of a Portuguese bank's direct-call term-deposit campaign. The dataset contains 41,188 client records across 21 variables, including client demographics (age, job, marital status, education), loan and credit status, contact-related fields (channel, month, day, call duration), campaign history (number of contacts, prior outcome), macroeconomic indicators (employment variation rate, consumer price index, Euribor 3-month rate, number employed), and the binary outcome variable, whether the client subscribed to a term deposit (y). The dataset is complete, with no missing values, which allowed the analysis to proceed directly to exploration without an imputation step.

## 2. Key Insights from the Visualizations

# 2.1 Overall campaign performance
Of the 41,188 contacts, only 4,640 (11.3%) resulted in a term deposit being opened, against 36,548 (88.7%) that did not. This heavy class imbalance is the single most important structural fact about the dataset: any dashboard or predictive model built on it must account for it, since a naive model predicting "no" for every client would already be ~89% accurate while being commercially useless.

# 2.2 Job and occupation
•	In absolute numbers, administrative staff and technicians produced the most successful subscriptions, simply because they are the largest groups contacted.
•	In relative terms (success rate within the group), students (~31%) and retirees (~25%) convert far better than any other occupation, roughly 3–4x the overall average.
•	Blue-collar and services roles show the lowest conversion, both in absolute and relative terms, suggesting these segments should be deprioritized or approached differently.

# 2.3 Education level
Clients recorded as illiterate (~22%) and those with an unknown education level (~15%) show the highest success rates, followed by university-degree holders (~14%). The basic.6y and basic.9y education tiers show the lowest conversion (~8%). This is a counter-intuitive pattern worth flagging in the dashboard: it likely reflects that the illiterate/unknown groups are small and skew toward retirees, rather than education being a direct driver of interest in term deposits.

# 2.4 Age
Deposit success rate shows a moderate positive correlation with age (r ≈ 0.55). When grouped into bands, clients under 25 and clients 65+ convert at markedly higher rates than the 25–54 middle-age bands, with the 65+ group reaching roughly 45%, by far the strongest single segment in the data. This U-shaped pattern (young and retired clients responding best) is one of the clearest actionable findings for campaign targeting.

# 2.5 Marital status
Married clients account for the largest number of successful subscriptions in absolute terms simply because they are the largest group contacted. However, single clients convert at a higher rate relative to the number contacted, and divorced/widowed clients convert least well of the three main categories.

# 2.6 Contact channel
Cellular contact substantially outperforms landline (telephone) contact, both in volume of successful subscriptions and in conversion rate. This supports a straightforward operational recommendation: prioritize mobile outreach over fixed-line calls.

# 2.7 Macroeconomic indicators
Employment variation rate, the Euribor 3-month rate, and the number of employees are strongly positively correlated, since all three move with the broader economic cycle. Campaigns run during periods of lower employment variation and lower interest rates tend to coincide with higher subscription rates, suggesting timing matters almost as much as who is being called.

## 3. Summary Table of Top-Converting Segments
Segment	Highest success rate	Approx. rate
Job	Student	~31%
Job	Retired	~25%
Education	Illiterate	~22%
Age group	65+	~45%
Contact channel	Cellular	~14–17%

## 4. Dashboard Structure & Recommendations
•	Dashboard: Page 1 (Overview) — KPI cards, outcome donut, and slicers for job, education, age band, and channel that cross-filter the page.
•	Dashboard: Page 2 (Segmentation) — bar charts of success rate by job, education, marital status, and age band.
•	Dashboard: Page 3 (Campaign & Economic Factors) — outcome by channel/month, macro indicators vs. monthly success rate, and prior-campaign outcome vs. current success rate.
•	Recommendation: prioritize students, retirees, and clients 65+ (2–4x average conversion) and shift landline effort to cellular.
•	Recommendation: treat call duration as a benchmarking variable only, since it is unknown before a call is placed.
•	Recommendation: time campaigns to periods of lower employment variation/Euribor, and correct for the ~89/11 class imbalance in any predictive model.

## 5. Conclusion
Campaign success is driven less by broad demographic categories and more by specific, actionable segments: retirees and students, older and younger clients, and cellular contact. Combined with the finding that macroeconomic conditions move together and correlate with performance, the bank can improve conversion by re-targeting high-response segments and timing campaigns to the interest-rate and employment cycle, rather than contacting the full client base uniformly.
<img width="504" height="683" alt="image" src="https://github.com/user-attachments/assets/837ba12d-bc61-4317-abaa-4182344650b4" />
