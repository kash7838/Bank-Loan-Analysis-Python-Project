# Bank Loan Analysis (Python)

> A clean, end‑to‑end exploratory analysis of retail bank loan data using Python and Jupyter. The project focuses on understanding portfolio health, customer segments, and drivers of repayments/shortfalls, with clear visuals and reproducible steps.

---

## 📌 Objectives

- Understand the composition of the loan portfolio across customer attributes (e.g., home ownership, purpose, terms).
- Analyze cash flows: funded amount, received amount, outstanding balance, and charge‑offs.
- Surface patterns and risk signals through exploratory data analysis (EDA) and visualizations.
- Build decision‑ready insights for business teams and set up a baseline for modeling.

---

## 🗂️ Project Highlights

- Intensive EDA over key borrower attributes and loan performance fields.
- Clean, publication‑quality charts to communicate portfolio composition and movement of cash flows.
- A reproducible notebook workflow (load → clean → analyze → visualize).
- Clear separation of data, notebooks, scripts, and reports for easy navigation.

> Example insight included in the notebook: a bar chart showing **Total Received Amount by Home Ownership category** with the buckets `MORTGAGE`, `RENT`, `OWN`, and `OTHER`. This view helps compare realized cash inflows across ownership segments and spot skew or concentration risk.  

---

## 🧰 Tech Stack

- **Language:** Python 3.10+  
- **Core Libraries:** `pandas`, `numpy`, `matplotlib`, `plotly` (optional for interactivity)  
- **Environment:** Jupyter Notebook

---

## 📁 Repository Structure

```
bank-loan-analysis/
├── data/                 # Raw / processed data (kept out of VCS if sensitive)
├── notebooks/
│   └── 01_eda_bank_loans.ipynb   # Main analysis notebook
├── scripts/
│   ├── load_data.py      # I/O helpers
│   ├── eda_utils.py      # Common EDA utilities & plotting functions
│   └── clean.py          # Data cleaning/feature typing
├── reports/
│   └── figures/          # Exported charts (PNG/SVG)
├── assets/               # Logos/illustrations used in the README
├── requirements.txt
└── README.md
```

> If your local structure differs, adjust paths in the notebook’s first cell.

---

## 🔍 Data at a Glance

Typical fields expected in the dataset (names may vary by source):

- **Loan identifiers:** `id`, `member_id`, `issue_d`
- **Loan attributes:** `term`, `int_rate`, `installment`, `grade`, `sub_grade`
- **Amounts:** `loan_amnt`, `funded_amnt`, `total_rec_prncp`, `total_rec_int`, `total_rec_late_fee`, `recoveries`
- **Status & risk:** `loan_status`, `delinq_2yrs`, `dti`, `emp_length`
- **Customer profile:** `home_ownership`, `annual_inc`, `purpose`, `addr_state`

> The notebook demonstrates grouping and aggregation over these fields to compare portfolio segments and realized cash flows.

---

## 🚦 Key EDA Questions Answered

- Which **customer segments** (e.g., home ownership, purpose) drive **higher received amounts** and **lower shortfalls**?
- How do **interest rate** and **term** correlate with **repayments** and **late fees**?
- What does the **distribution of loan statuses** tell us about portfolio health?
- Are there **outliers** in funded amounts or income that require special handling?

---

## 📊 Visualizations

- Distribution plots for major numeric features (amounts, interest rate, income).  
- Categorical breakdowns (stacked/clustered bars) for ownership and loan purpose.  
- Cash‑flow aggregations: **Total Received Amount** by borrower segments.  
- Time‑based trends (issue date vs. total receivables), if a time field is present.

> Figures are saved under `reports/figures/` when you run the notebook.

---

## ⚙️ Setup & Usage

### 1) Clone & create a virtual environment
```bash
git clone https://github.com/<your-username>/bank-loan-analysis.git
cd bank-loan-analysis

python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows
.venv\Scripts\activate
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Launch Jupyter and run the notebook
```bash
jupyter lab  # or: jupyter notebook
```

Open `notebooks/01_eda_bank_loans.ipynb` and run all cells.  
Charts will export to `reports/figures/` if you keep the default settings.

---

## ✅ Results & Business Takeaways

- Clear view of **where cash inflows are realized** (e.g., by home ownership and purpose).  
- Ability to spot **concentrations and exposure** (e.g., a heavy tilt toward a single segment).  
- Early indicators for **risk controls** and **pricing** (e.g., interest rate bands and term interactions).  
- A repeatable workflow that can be extended into **scorecarding** or **default‑risk modeling**.

---

## 🚀 Next Steps (Optional Extensions)

- Enrich the dataset with **bureau scores** or **macro features** (unemployment, CPI).  
- Derive **behavioral features** (payment cadence, utilization, rolling delinquencies).  
- Build a baseline **probability of default** model and a **loss given default** estimate.  
- Deploy an **interactive dashboard** (Streamlit/Plotly Dash) for non‑technical stakeholders.

---

## 🧪 Reproducibility

- Random seeds set where applicable.  
- Notebook cells are idempotent; re‑running produces the same figures given the same inputs.  
- Style utilities in `eda_utils.py` ensure consistent charts across analyses.

---

## 📄 License

MIT (update as needed).

---

## 🙏 Acknowledgements

- Thanks to open‑source contributors of `pandas`, `numpy`, `matplotlib`, and Jupyter.
- Dataset source intentionally omitted in this public README; replace with your internal or public source as appropriate.

---

> _Last updated: 2025-08-25_
