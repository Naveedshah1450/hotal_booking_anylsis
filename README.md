# 🏨 Hotel Booking Cancellation Analysis — EDA Project

## 📌 Problem Statement

Hotels lose significant revenue every year due to unpredictable booking cancellations, which disrupt inventory planning, staffing, and pricing strategy. This project analyzes 119,390 hotel booking records to identify the strongest predictors of cancellation, enabling hotel management to proactively flag high-risk bookings (e.g., through stricter deposit policies or targeted confirmation calls) and reduce revenue loss from last-minute cancellations.

## 📊 Dataset

- **Source:** [Kaggle — Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
- **Size:** 119,390 rows × 32 columns
- **Target variable:** `is_canceled` (1 = cancelled, 0 = not cancelled)
- **Time span:** Bookings from City Hotel and Resort Hotel

## ❓ Business Questions

1. What is the overall cancellation rate, and how does it differ between City Hotel and Resort Hotel?
2. How does `lead_time` (days between booking and arrival) affect the probability of cancellation?
3. Which countries have the highest cancellation rates?
4. What impact does `deposit_type` have on cancellation behavior?
5. Does a guest's `previous_cancellations` history predict future cancellations?
6. What does a "high-risk" booking profile look like when combining multiple factors?
7. Is there a relationship between `adr` (average daily rate) and cancellation?

## 🗂️ Project Structure

```
hotel-booking-eda/
│
├── README.md                  <- Project overview (this file)
├── data/
│   └── hotel_bookings.csv     <- Raw dataset (or a link if too large for GitHub)
├── notebooks/
│   └── hotel_booking_eda.ipynb   <- Main analysis notebook
├── images/
│   └── (chart screenshots used in README/report)
├── report/
│   └── Hotel_Booking_EDA_Report.docx   <- Formal write-up
└── requirements.txt            <- Python libraries used
```

## 🛠️ Tools & Libraries

- Python (Pandas, NumPy)
- Matplotlib, Seaborn
- SciPy (chi-square, t-test for significance testing)
- Jupyter Notebook
- MySQL (for querying the dataset directly, portfolio-relevant skill)

## 🔍 Methodology

1. **Data Cleaning** — handled missing values in `country`, `agent`, `company`; fixed data types
2. **Univariate Analysis** — distribution of lead_time, adr, stay length, guest counts
3. **Bivariate Analysis** — each feature vs. `is_canceled`
4. **Outlier Detection** — IQR method applied to `lead_time` and `adr`
5. **Statistical Testing** — chi-square test for categorical association, t-test for numeric differences
6. **Cross-tabulation** — deposit_type × cancellation, hotel_type × cancellation
7. **Risk Scoring** — composite boolean-mask-based high-risk booking flag

## 💡 Key Insights

*(Fill in after running your analysis — example format below)*

- City Hotel bookings cancel at a higher rate than Resort Hotel bookings
- Bookings with `lead_time` > 100 days show significantly higher cancellation risk
- `deposit_type = Non Refund` is counter-intuitively associated with much higher cancellations
- Guests with prior cancellation history are far more likely to cancel again

## ✅ Recommendations

*(Fill in after analysis — example format below)*

- Introduce partial deposits for bookings with lead_time > 100 days
- Flag and follow up with guests who have previous_cancellations > 0
- Reassess "Non Refund" deposit policy — it may be attracting fraudulent or speculative bookings

## 📎 How to Run

```bash
git clone <your-repo-link>
cd hotel-booking-eda
pip install -r requirements.txt
jupyter notebook notebooks/hotel_booking_eda.ipynb
```

## 👤 Author

Syed Naveed Ur Rehman Bokhari
[SYED NAVEED ] | [Naveedshah1450]
