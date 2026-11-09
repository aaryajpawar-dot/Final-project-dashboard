# SWYNEX Interactive Dashboard: Fraud Detection Command Center

Task 4 of my Data Analysis internship at **SWYNEX Technologies**. An interactive, offline-ready dashboard that explores credit card fraud patterns in 284,807 real transactions.

## 🔗 Live Dashboard
**[Open the interactive dashboard](https://pastoral-tuba-fze.julius.site)**

Or download `index.html` from this repo and open it in any browser. It works offline and needs no installation.

## 🎯 Objective
Turn a highly imbalanced fraud dataset into a dashboard with KPIs, charts and filters, so that when and where fraud concentrates is easy to see.

## 📁 Dataset
- **Name:** Credit Card Fraud Detection (ULB Machine Learning Group / Worldline), from Kaggle
- **Coverage:** European cardholders, two days in September 2013
- **Size:** 284,807 transactions, of which 492 are fraud (about 0.17%)
- **Columns:** `Time`, `V1`-`V28` (anonymized PCA features), `Amount`, `Class` (1 = fraud, 0 = normal)
- **Sample file:** `creditcard_sample.csv` has all 492 frauds plus 20,000 random normal rows (seed 42), to stay under GitHub's size limit. Its fraud share is deliberately enriched and is **not** the real fraud rate.

## 📈 Dashboard Features

**KPIs**
- Fraud prevalence
- Fraud value share
- Average fraud vs. normal amount
- Data coverage
- Peak fraud hour

**Charts**
- Fraud through the hours (count and rate)
- Fraud rate by amount band
- Amount distribution, fraud vs. normal
- Day 1 vs. Day 2 comparison
- Class imbalance donut
- Heatmap of hour × amount band
- Strongest V-feature differences between fraud and normal
- Priority review table of the 10 highest-value frauds

**Interactivity**
- Filters: hour range, amount range, day and class, plus a reset button
- Clicking a chart bar, cell or slice cross-filters the whole dashboard
- Auto-updating key insights
- Export of the sample as CSV

## 🔍 Key Findings
1. **Fraud is rare:** only 492 of 284,807 transactions (about 0.17%) are fraudulent, so accuracy is a misleading metric. A model that always predicts "normal" would be about 99.83% accurate.
2. **Peak fraud hour:** [add from dashboard, e.g. "Hour X has the highest fraud rate"]
3. **Amount behaviour:** [add, e.g. "Fraud transactions are typically smaller / larger than normal ones"]
4. **Amount bands:** [add the band with the highest fraud rate]
5. **Day comparison:** [add whether Day 1 or Day 2 had more fraud]
6. **Top anonymized features:** [add the top 2-3 V-features that differ most, e.g. V14, V17]

## ⚠️ Methodology and Limitations
- `Time` is seconds since the first transaction, not a clock time. "Hour" means elapsed hour modulo 24.
- V1-V28 are anonymized PCA components, so no meaning is assigned to them and no causal claims are made.
- All KPI cards, transaction charts and insights use all 284,807 records. Filtered detail views use the labelled sample.
- "Amount lost to fraud" is the sum of flagged transaction amounts, not verified net loss.
- This dashboard is descriptive, not a fraud detection model, and shows historical data from only two days.

## 🛠️ Tools Used
- Julius AI (analysis and dashboard)
- Python (pandas) for cleaning and analysis
