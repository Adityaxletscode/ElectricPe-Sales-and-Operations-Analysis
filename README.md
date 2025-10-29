# 📊 ElectricPe Sales and Operations Analysis

## 🧠 Project Overview
This project focuses on analyzing and optimizing the **sales pipeline** by identifying trends in **lead management**, **conversion efficiency**, **customer satisfaction**, and **operational bottlenecks**.  
The goal is to support **data-driven decision-making** that helps increase conversion rates, reduce turnaround times, and enhance customer experience across multiple store locations.

---

## 📂 Dataset Summary

- **Rows:** 1,000  
- **Columns:** 14  

### Key Features:
- Lead journey details – *Lead ID, Store Name, Lead Type, Lead/Pre-Booking/Booking/Delivery Dates*  
- Cancellation details – *Status, Reason*  
- Customer service data – *Service Follow-up Date, Customer Rating*  
- Operational metrics – *TAT (Turnaround Time) for Pre-Booking, Booking, Delivery*  
- Segmentation – *Store, Lead Type, Date*

---

## 🧹 Data Cleaning

1. **Handling Missing Values**
   - Filled missing *Cancellation Reason* with `"Not Cancelled"` for non-cancelled leads.  
   - Retained missing dates and ratings to ensure accurate stage-wise calculations.

2. **Standardizing Date Formats**
   - Converted all date columns to datetime using `pd.to_datetime()` for consistent sequencing and time-based analysis.

3. **Standardizing Categorical Values**
   - Cleaned categorical fields using `.str.title().str.strip()` to unify inconsistent entries (e.g., “hot”, “HOT” → “Hot”).

4. **Cleaning Numeric Data**
   - Converted *TAT* and *Customer Rating* columns to numeric for statistical analysis.

5. **Removing Duplicates**
   - Dropped duplicate entries by *Lead ID* to ensure data integrity.

---

## 📈 Exploratory Data Analysis (EDA)

### 1. Basic Overview
- Verified dataset dimensions: `1000 rows × 14 columns`.  
- Inspected random samples for structure and consistency.

### 2. Missing Values
- Identified missingness primarily in stage dates and customer ratings.  
- Confirmed no duplicate *Lead IDs*.

### 3. Value Distribution
- **Lead Type:** Warm (509), Hot (303), Cold (188)  
- **Cancellation Status:** Not Cancelled (729), Cancelled (271)  
- **Stores:** Bangalore, Chennai, Delhi, Mumbai — distributed nearly evenly.

### 4. Descriptive Statistics
- **Customer Rating:** Range 0–10, Mean ≈ 4.85  
- **TAT (Days):** Calculated average and range for Pre-Booking, Booking, and Delivery stages.

---

## 🔍 Key Analyses

### 1. Conversion Rates
Calculated stage-wise conversion percentages (Lead → Pre-Booking → Booking → Delivery).

### 2. Store-wise Analysis
- Compared lead counts, conversion rates, and average TATs per store.  
- Identified top-performing and slower stores.

### 3. Cancellation Analysis
- Grouped cancellations by store and reason.  
- Found top reasons: *Changed Mind*, *Price*, *Financing Issue*, *Model Unavailable*.

### 4. Lead Type Segmentation
- Analyzed Hot/Warm/Cold leads overall and by store for targeted follow-up.

### 5. Net Promoter Score (NPS)
- Defined:
  - **Promoters:** Ratings 9–10  
  - **Detractors:** Ratings 0–6  
- Calculated NPS = `%Promoters − %Detractors`  
- All stores showed negative NPS, signaling areas for service improvement.

### 6. High-Potential Lead Extraction
Filtered leads that met these conditions:
- `Lead Type = Hot`  
- `Not Cancelled`  
- `Customer Rating ≥ 9`  
- `Fast Delivery ≤ 5 days`

These were flagged for **priority follow-up**.

---

## 📊 Power BI Dashboard

An **interactive Power BI dashboard** was built to visualize and interact with insights derived from the analysis.  
It includes:
- Conversion funnel metrics  
- Store-wise TAT performance  
- Lead segmentation  
- Cancellation trends  
- NPS by store  

🖼️ **Dashboard Preview:**  
![Sales and Operations Dashboard](https://github.com/Adityaxletscode/ElectricPe-Sales-and-Operations-Analysis/blob/main/Dashboard.png)

---

## 💡 Business Recommendations

1. **Reduce Cancellations**
   - Address top reasons: *Changed Mind, Price, Financing Issue, Model Unavailable*.  
   - Provide transparent pricing, financing options, and proactive customer engagement.

2. **Improve NPS**
   - Focus on stores with negative NPS.  
   - Enhance customer service, delivery experience, and post-sale interactions.

3. **Accelerate Delivery Times**
   - Replicate best practices from stores with shorter TATs.  
   - Optimize logistics and internal coordination in slower locations.

4. **Prioritize High-Potential Leads**
   - Run targeted campaigns for Hot, non-cancelled leads with high satisfaction ratings.  
   - Implement automated follow-ups to boost conversions.

---

## 🏁 Conclusion
This analysis brings clear visibility into:
- **Pipeline efficiency**
- **Customer satisfaction**
- **Operational bottlenecks**
- **Store-wise performance**

By combining **Python-based analytics** with **Power BI visualization**, this project empowers the organization to:
- Decrease cancellations  
- Enhance conversions  
- Improve customer experiences  
- Streamline operations through data-backed strategies.

---

## 🧰 Tech Stack
- **Languages:** Python(Pandas)  
- **Visualization:** Power BI  
- **Data Source:** Internal sales and operations dataset (1,000 records)  

---


