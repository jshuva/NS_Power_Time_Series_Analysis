# MCDA 5580: Presentation Script & Strategy
**Title:** Nova Scotia Power Electricity Analytics
**Presenters:** Speaker 1, Speaker 2, Speaker 3 
**Total Time:** 20 Minutes (approx. 6–7 minutes per person) + 5 Min Q&A
**Dashboard Link:** [Nova Scotia Power Dashboard](https://public.tableau.com/app/profile/jayanta.sarker3104/viz/NovaScotiaPowerElecticityAnalysis/NovaScotiaPowerElectricityAnalytics)

---

## 🎤 Speaker 1: Introduction, Dataset Overview & Key EDA Findings
**(Estimated Time: 6 minutes)**

**1. Introduction & Executive Summary (1.5 mins)**
*   **Hook**: "Good morning everyone. As Nova Scotia Power transitions toward cleaner energy and faces increasingly volatile weather, understanding grid demand has never been more critical."
*   **Objective**: "Our team was tasked with analyzing 10 years of hourly electricity data across 5 Nova Scotia regions. Today, we'll walk you through our key insights, our forecasting models, the anomalies we detected, and finally, actionable business recommendations for NSPI."

**2. Dataset Overview & Data Quality (1.5 mins)**
*   **The Data**: Briefly explain the scale—processing over 438,000 hourly records spanning 2015 to 2024.
*   **Feature Engineering**: "To give our models the best chance at success, we engineered custom features like 24-hour lagged consumption, 7-day rolling averages, and categorical temperature bins (Cold, Mild, Hot), because raw temperature isn't as predictive as categorizing the *extremes*."

**3. Key Exploratory Data Analysis (EDA) Findings (3 mins)**
*   **What patterns stood out immediately?** (Focus on the *Insights*)
    *   **Hourly & Weekly Cycles**: "We discovered a massive surge in demand consistently clustering between 4 PM and 8 PM on weekdays as people return home from work."
    *   **Seasonality & Temperature**: "Winter definitively drives our highest loads across the province due to heating demands. This perfectly aligns with the strong negative correlation we found between temperature drops and consumption spikes."
    *   **Regional Differences**: "Unsurprisingly, Halifax holds the lion's share of the load compared to rural counties like Annapolis Valley, commanding a completely different baseline."
*   **Transition to Speaker 2**: "Knowing these baseline cycles is great, but NSPI needs to know what happens *next week*, and they need to identify when things go wrong. I'll pass it to [Speaker 2] to talk about our Machine Learning models."

---

## 🎤 Speaker 2: Machine Learning - Forecasting & Anomaly Detection
**(Estimated Time: 7 minutes)**

**1. Time Series Forecasting (Task 2A) (3.5 mins)**
*   **Approach**: "For short-term 7-day forecasting, we didn't just stop at one method. We deployed both **Facebook Prophet** (excellent at capturing human-driven weekly/daily seasonality) and an **LSTM Neural Network** (excellent at learning complex sequential dependencies)."
*   **The Forecast**: "Focusing on Halifax, we trained the models on historical data and tested them on the final 168 hours."
*   **Insights over Methodology**: Don't get bogged down in hyper-parameters. Say, "Both models did a fantastic job tracing the extreme peaks and valleys of daily usage, but when looking at the Mean Absolute Percentage Error (MAPE), our [State whether Prophet or LSTM performed better] edged out the competition, proving highly reliable for short-term grid planning."

**2. Anomaly Detection (Task 2B) (3.5 mins)**
*   **Approach**: "Standard forecasting handles the 'normal' days, but what about the outliers? Storms, freezes, and outages. We implemented an **Isolation Forest**—an unsupervised machine learning algorithm designed to flag extreme deviations."
*   **What anomalies did we find?** 
    *   "The model successfully isolated specific periods of highly unusual consumption. We found massive **Spikes** usually aligning with sudden extreme weather, and sudden **Drops**, which align heavily with partial power outages on the grid or deliberate demand-response events."
*   **Validation**: "When we checked the algorithm's decisions against the ground-truth anomaly flags, it performed incredibly well, proving NSPI can use this in real-time to alert dispatchers to grid stress."
*   **Transition to Speaker 3**: "But numbers in a Jupyter Notebook don't help executives make decisions. [Speaker 3] is going to take control of the screen to demonstrate the live Tableau Dashboard we built for NSPI management."

---

## 🎤 Speaker 3: Live Tableau Demo & Business Recommendations
**(Estimated Time: 7 minutes)**

**1. Tableau Live Demo (4 mins)**
*   *Action: Pull up the [Tableau Public Link](https://public.tableau.com/app/profile/jayanta.sarker3104/viz/NovaScotiaPowerElecticityAnalysis/NovaScotiaPowerElectricityAnalytics) on the projector.*
*   **Walkthrough & Key Insights**: "This dashboard is designed for leadership to track grid health at a glance. Let's look at a few powerful insights our algorithm uncovered:"
    1.  **Renewable & Emissions Trend**: "As the grid shows steady long-term growth in the percentage of renewable energy sources, overall CO₂ emission volume directly trends downward as renewable grid integration increases."
    2.  **Heatmap Confirmation**: "The heatmap proves that peak energy usage clusters heavily between 4 PM and 8 PM on weekdays across all regions."
    3.  **Forecast Chart Validation**: "And here is our 7-day Forecast vs Actual curve. You can see the forecasting model accurately captures the daily demand valleys and peaks over the final 7 days, proving its reliability."
*   **Demonstrate Interactivity (Required)**: 
    *   Click through the **Region** and **Year** filters to prove the entire dashboard dynamically updates. (e.g., "Notice how when I filter down to just Cape Breton during the winter months, the usage and emission trends shift...").

**2. Executive Business Recommendations (3 mins)**
*   "Based on our total analysis, here is what NSPI should do differently:"
    1.  **Targeted Peak-Shaving Programs**: "Because our heatmap definitively proves peak stress happens from 4-8 PM on weekdays, NSPI should introduce aggressive 'Time-of-Use' pricing to financially incentivize Halifax residents to run dishwashers and laundry machines after 9 PM."
    2.  **Automated Alerting**: "NSPI should integrate our Isolation Forest model directly into their control room. By automatically flagging 'Spike' and 'Drop' anomalies in real-time, dispatchers can react to grid-stress events minutes before a transformer blows."
    3.  **Renewable Battery Integration**: "Our charts show a steady rise in renewable percentage, but solar and wind fluctuate. NSPI should invest in grid-scale battery storage specifically scaled to handle the Winter seasonal peaks we identified in our EDA."

**3. Conclusion & Q&A (< 1 min)**
*   "That concludes our analysis. Thank you for your time, we'd like to open the floor to any questions."

---

## 💡 Quick Presentation Tips for the Group
1.  **Pacing**: 20 minutes goes fast. Practice your transitions so you aren't awkwardly handing off the microphone. 
2.  **No Code on Screen!**: The executives do not care what Python library you imported. Focus entirely on *what the data tells you* and *how it saves or makes money*.
3.  **Q&A Prep**: Have one group member prepared to answer a question about "Why did you choose Prophet/LSTM?" and another prepared to answer "What features did you engineer and why?"
